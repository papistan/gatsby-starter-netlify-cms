---
author: johnkodumal
comments: false
date: 2015-02-24 20:25:28+00:00
layout: post
link: https://launchdarkly.com/blog/packaging-go-microservices-for-aws-deployment-using-circleci/
slug: packaging-go-microservices-for-aws-deployment-using-circleci
title: Packaging Go Microservices for AWS Deployment using CircleCI
description: Most of LaunchDarkly’s backend systems are written in Go. We have a microservice-based architecture, so we have about 10 distinct standalone binaries (either web services or asynchronous worker processes) that we deploy to AWS. We have a small engineering team, so it’s important that we can package and deploy our code with minimal overhead.
wordpress_id: 29
categories:
  - Continuous Delivery
  - DevOps
---

Most of LaunchDarkly's backend systems are written in Go. We have a microservice-based architecture, so we have about 10 distinct standalone binaries (either web services or asynchronous worker processes) that we deploy to AWS.

We have a small engineering team, so it's important that we can package and deploy our code with minimal overhead. Out of the box, Go provides an amazing set of tools that make this manageable, but we found we needed to hunt around to fill in a few gaps in the toolchain. Here are the extra tools we use to get our Go code packaged and ready for deployment.

## Repeatable builds with Godep

One of the first issues we saw with Go was that out of the box, the `go` tool doesn't give you any way to version dependencies. This seems like a big oversight to me, but perhaps it makes more sense in a world where you have [one monolithic repository](http://paulhammant.com/2013/05/06/googles-scaled-trunk-based-development/).

At any rate, we have code in about 20 distinct repositories, so versioned dependencies and repeatable builds are essential for us. We use [Godep](https://github.com/tools/godep) to handle versioning in our Go builds.

Godep is fairly simple. `godep save` stores version metadata (for us, git sha's) for your dependencies into a `Godeps/Godep.json` file in your repository root. It also stores all your dependency sources in a `Godeps/_workspace` directory. You commit this entire directory structure [including the `_workspace`](https://github.com/tools/godep/pull/123) into your repository. Instead of running `go build`, you compile with `godep go build`. When you want to update a dependency, do so in your normal go path and then invoke `godep update IMPORT_PATH`. Simple and effective.

One thing that wasn't obvious to us was how to structure "library" packages to work best with `go` and `godep`. By that, I mean repositories that consist of several packages that aren't necessarily tied together with a top-level "main" package. We have a repository that serves as our ubiquitous "bucket" of essential utility code. We call it `foundation`, and it has packages for things like epoch times and richer error types. The directory structure for `foundation` looks like this:

    foundation/
       Godeps/
       ftime/
        ftime.go
       ferror/
        ferror.go
       ...

There's no `go` source in the top-level of the repository, so `go build` complains:

    <code>$ godep go build
    can't load package: package github.com/launchdarkly/foundation: no buildable Go source files</code>

The right thing to do is to point `go` to each of the package subdirectories:

    <code>godep go build ./...</code>

Typing `./...` is pretty thoroughly ingrained into our muscle memories now. We have to type it every time we build our foundation, as well as every time we want to do a wholesale update of all the foundation packages in a dependent repository: `godep update github.com/launchdarkly/foundation/...`

## Cross compiling

Go compiles to machine code, so binaries are platform-dependent. We do all our local development on OS X, but for staging and production we need to build Linux targets. Again, reproducible builds are important to us-- we want to be able to build our production artifacts for Linux on our OS X boxes if necessary. For that, we use a cross-compilation tool called `goxc`.

`goxc` is pretty straightforward to set up. We store our configuration in `.goxc.json` files in each of our repositories. For a simple worker or web service, our `.goxc.json` files look like this:

    {
      "ArtifactsDest": "./pkg",
      "Tasks": [
        "xc",
        "archive-tar-gz"
      ],
      "BuildConstraints": "linux,!arm darwin",
      "ConfigVersion": "0.9",
      "Env": [
        "GOPATH={{.Env.PWD}}{{.PS}}Godeps{{.PS}}_workspace{{.PLS}}{{.Env.GOPATH}}"
      ]
    }

This simple configuration runs the cross compiler and packages a `.tar.gz` archive of our binary. The `BuildConstraints` line uses Go's [build constraints notation](http://golang.org/pkg/go/build/)-- the line we use compiles for Linux and OS X, but disables Linux ARM (which we don't need to target). The `GOPATH` setting took a bit of figuring out-- `goxc` lets you specify a template format including variables like the current working directory (`PWD`), a platform specific path separator (`PS`) and path list separater (`PLS`), etc. Our [GOPATH setting](https://github.com/laher/goxc/issues/28) points `goxc` to our `Godeps` directory and falls back to our environment-specified `GOPATH`. The `Godeps` directory alone might be preferable-- ensuring that your build doesn't depend on local copies of packages:

    <code>GOPATH={{.Env.PWD}}{{.PS}}Godeps{{.PS}}_workspace</code>

Another useful trick that we use is to pass a `build-ldflags` flag to `goxc`. We use this to inject a git SHA into our binaries in a `Version` variable. This makes it extremely easy to figure out _exactly_ what version of a service is running at runtime. Versions for us are just git SHAs-- we don't bother with the overhead of maintaining semantic version numbers for our services. In our Go code, all we have to do is this:

    package main

    var Version="DEV"

Once we've got this, we wrap up our `goxc` invocation into a small script called `package.sh` that sets the `VERSION` variable to our current git sha:

    #!/bin/bash
    REV=$(git rev-parse HEAD | cut -c1-6)
    if [ -z "$CIRCLE_ARTIFACTS" ]; then
      DEST="./pkg"
    else
      DEST="${CIRCLE_ARTIFACTS}"
    fi
    goxc -wd=. -build-ldflags="-X main.Version ${REV}" -d=${DEST}

When built locally with `go build` or `godep go build`, the `Version` is set to `"DEV"`, but the packaged binary will overwrite the variable with a git SHA.

## CircleCI setup

Notice how we set the destination directory for our archive based on the `$CIRCLE_ARTIFACTS` environment variable. We use [CircleCI]("http://circleci.com) to build our binaries. The symlink trickery we do is necessary to make our "library" repositories build on CircleCI-- by default, checked-out repositories on Circle don't seem to be part of the Gopath. Here's what a basic `circle.yml` setup looks like for most of our workers:

    dependencies:
      pre:
        - rm -rf ~/.go_workspace/src/github.com/launchdarkly/service-name
        - mkdir -p ~/.go_workspace/src/github.com/launchdarkly/
        - ln -s ~/service-name ~/.go_workspace/src/github.com/launchdarkly/service-name
        - go get github.com/tools/godep
      override:
        - godep go build
      post:
        - ./scripts/package.sh
    test:
      override:
        - godep go test

## Uploading artifacts

We use ansible for our deploy scripts, and they're set up to pull artifacts from S3. All of our Circle builds run the following `upload_to_s3.sh` script:

    #/bin/bash
    service=YOUR_SERVICE_NAME
    file=${CIRCLE_ARTIFACTS}/snapshot/${service}_linux_amd64.tar.gz
    sha=`echo ${CIRCLE_SHA1} | cut -c1-6`
    target=${service}/${service}_${sha}.tar.gz
    bucket=YOUR_S3_BUCKET
    resource="/${bucket}/${target}"
    contentType="application/x-compressed-tar"
    dateValue=`date -R`
    stringToSign="PUT\n\n${contentType}\n${dateValue}\n${resource}"
    s3Key=$S3_KEY
    s3Secret=$S3_SECRET
    signature=`echo -en ${stringToSign} | openssl sha1 -hmac ${s3Secret} -binary | base64`
    response=`curl -s -o /dev/null -w "%{http_code}" -X PUT -T "${file}" \
      -H "Host: ${bucket}.s3.amazonaws.com" \
      -H "Date: ${dateValue}" \
      -H "Content-Type: ${contentType}" \
      -H "Authorization: AWS ${s3Key}:${signature}" \
      https://${bucket}.s3.amazonaws.com/${target}`
    echo "Upload status code: ${response}"
    if [ $response -ne "200" ] ; then exit 1 ; fi

This script should be pretty re-usable-- change the service and bucket names, and enter your `S3_KEY` and `S3_SECRET` into CircleCI's environment variables, and you're good to go. We tell CircleCI to upload the artifacts as part of a "deployment" step (even though we don't use CircleCI to actually deploy to EC2):

    deployment:
      s3:
        branch: /.*/
        commands:
          - ./scripts/upload_to_s3.sh

Again, you can customize this-- for example, you may only want to push artifacts built from `master` to S3.

## Conclusion

None of this was incredibly complex, and that's a testament to how good the Go tooling is out of the box. Going from an empty repository to a new Go microservice running in production is remarkably easy. In fact, it's so easy that we've automated it (well, everything except writing the actual service). We've created a [giter8](https://github.com/n8han/giter8) template (open-sourced on [GitHub](https://github.com/launchdarkly/go-micro.g8) that sets up a simple Go program with `goxc` cross-compilation, CircleCI tests and artifact packaging, and S3 artifact upload:

    <code>$ g8 launchdarkly/go-micro.g8
    name [oddjob]: your_service_name
    github_username [launchdarkly]: your_username_or_org
    s3_bucket [launchdarkly-artifacts]:
    Template applied in ./your_service_name</code>

Once you've configured your build on CircleCI (including setting the `S3_KEY` and `S3_SECRET` environment variables) and pushed your new repository to GitHub, you'll see artifacts uploaded to your S3 bucket. From there, we use ansible scripts (which I haven't covered in this post) to actually deploy artifacts onto EC2 instances.

---

###### _ LaunchDarkly helps you build better software faster with feature flags as a service. Start your free trial [now](https://app.launchdarkly.com/signup#/?utm_source=launchdarkly_blog&utm_medium=organic). _

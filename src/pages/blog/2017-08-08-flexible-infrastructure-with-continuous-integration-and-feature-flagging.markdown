---
author: Jwin
comments: false
date: 2017-08-08 16:56:59+00:00
layout: post
link: https://launchdarkly.com/blog/flexible-infrastructure-with-continuous-integration-and-feature-flagging/
slug: flexible-infrastructure-with-continuous-integration-and-feature-flagging
title: Flexible Infrastructure with Continuous Integration and Feature Flagging
wordpress_id: 1813
categories:
- Continuous Delivery
- Feature Management
---

I'm incredibly excited to be LaunchDarkly’s first solutions engineer. During my first week I got to learn about some of the clever ways we do [feature management](https://launchdarkly.com/use-cases/?utm_source=launchdarkly_blog&utm_medium=organic). Not only do we use feature flags to control the release of fixes and new features, but we also use them to manage the health of our infrastructure in production. I’ve been a part of a number of teams, and I’ve never seen a more advanced development pipeline.

Normally, dealing with issues in production can be a frightening and time-consuming experience, but adopting a mature continuous delivery pipeline can allow you to react faster and be proactive. Continuously integrating and deploying makes getting fixes into your production code a trivial task, but using feature flagging takes it to the next level and lets you put fixes in place for potential future pain points that you can easily enable without having to do another deploy.

One common problem is handling extreme server load. This is managed easily with LaunchDarkly. Imagine you have a server that is pulling time-sensitive jobs from a queue, but the queue fills faster than the server can handle it, and causes all jobs to fail. In situations like these it would be better to at least get some of the jobs done, instead of none of them. This is concept is known as [“bend-don't-break”.](https://insights.sei.cmu.edu/devops/2015/04/build-devops-tough.html)

I built a proof of concept using Python and rabbitMQ which demonstrates how you could use LaunchDarkly’s dashboard to control what percentage of jobs get done, and the rest get thrown away. If the worker takes too long to get to the job, the job fails. As you see the queue grow you can manage it easily with feature flags.

It consists of two scripts, taskQueuer and taskWorker. The taskQueuer adds imaginary time-sensitive jobs to the queue; the rate is configurable using feature flags.

    
    #!/usr/bin/env python
    import pika
    import time
    import json
    
    import sched
    from datetime import datetime 
    from datetime import timedelta 
    
    import ldclient
    
    # setup launch darkly client
    ldclient.set_sdk_key("YOUR_SDK_KEY")
    client = ldclient.get()
    user = { 'key': "lddemo" }
    
    # setup rabbitMQ client
    connection = pika.BlockingConnection(pika.ConnectionParameters(host='localhost'))
    channel = connection.channel()
    channel.queue_declare(queue='lddemo_task_queue', durable=True)
    
    s = sched.scheduler(time.time, time.sleep)
    def queue_job(sc):
    
      queue = channel.queue_declare(queue='lddemo_task_queue', durable=True, passive=True)
      print(' [   ] Queued length: ' + str(queue.method.message_count))
    
      channel.basic_publish(exchange='',
                            routing_key='lddemo_task_queue',
                            body=(datetime.now() + timedelta(seconds=10)).isoformat(),
                            properties=pika.BasicProperties(
                              delivery_mode = 2, # make message persistent
                            ))
    
      delay = float(client.variation('queue-rate', user, 1))
      s.enter(delay, 1, queue_job, (sc,))
    
    s.enter(1, 1, queue_job, (s,))
    s.run()
    
    print(' [ * ] Queuing messages. To exit press CTRL+C')
    


The taskWorker removes one job from the queue and processes it. One job takes one second. If tasks are queued faster than the worker can process it, the queue fills up and the worker will begin failing. To protect against this, you can use the "skip rate" feature flag to allow the worker to drop a certain percentage of jobs on the floor.

    
    #!/usr/bin/env python
    import pika
    import time
    import json
    
    import random
    from datetime import datetime 
    from dateutil import parser
    
    import ldclient
    
    # setup launch darkly client
    ldclient.set_sdk_key("YOUR_SDK_KEY")
    client = ldclient.get()
    user = { 'key': "lddemo" }
    
    # setup rabbitMQ client
    connection = pika.BlockingConnection(pika.ConnectionParameters(host='localhost'))
    channel = connection.channel()
    channel.queue_declare(queue='lddemo_task_queue', durable=True)
    
    successes=0
    jobs=0
    
    def process_job(ch, method, properties, body):
      global successes
      global jobs
    
      skip_rate = int(client.variation("skip-rate", user, "0"))
      print(" [   ] Skip Rate: " + str(skip_rate))
      if (random.randrange(100) < skip_rate): print(" [ X ] Skipping") else: print(" [...] Processing") time.sleep(1) if (datetime.now() > parser.parse(body)):
          print(" [ X ] Failed")
        else:
          print(" [ O ] Success")
          successes = successes + 1
      jobs = jobs + 1
      success_rate = successes*100/jobs
      print( "success rate: (" + str(successes) + "/" + str(jobs) + ") " + str(int(success_rate)) + "%" )
      ch.basic_ack(delivery_tag = method.delivery_tag)
    
    channel.basic_qos(prefetch_count=1)
    channel.basic_consume(process_job, queue='lddemo_task_queue')
    channel.start_consuming()
    
    print(' [ * ] Waiting for messages. To exit press CTRL+C')
    


The concept of using LaunchDarkly as a control panel to manage the operation of your app is really cool and opens up a world of possibilities beyond simply percentage rollouts and canary releases. If you have an interesting implementation, get in touch with us at hello@launchdarkly.com and maybe we'll feature it!

More about tough devops: [https://insights.sei.cmu.edu/devops/2015/04/build-devops-tough.html](https://insights.sei.cmu.edu/devops/2015/04/build-devops-tough.html)
More about using Python with rabbitMQ: [https://www.rabbitmq.com/tutorials/tutorial-one-python.html](https://www.rabbitmq.com/tutorials/tutorial-one-python.html)
More about LaunchDarkly's stack: [https://stackshare.io/launchdarkly/how-launchdarkly-serves-over-4-billion-feature-flags-daily](https://stackshare.io/launchdarkly/how-launchdarkly-serves-over-4-billion-feature-flags-daily)

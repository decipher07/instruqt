---
slug: 04-running-application
id: uhop2qxgbwg0
type: challenge
title: Access the application running on OpenShift
tabs:
- title: Terminal 1
  type: terminal
  hostname: crc
- title: Web Console
  type: service
  hostname: crc
  path: /
  port: 30001
- title: Visual Editor
  type: code
  hostname: crc
  path: /root
difficulty: basic
timelimit: 300
---
After the previous step build finishes, it will take less than a minute for the application to become available.

### Check the application logs

Now that the application is up and running you can check the logs to check how is everything going on.

Let's use the OpenShift CLI tool to connect with the deployment and view the pod's log.

Use the following command to retrieve the logs:

`oc -n messaging logs -f dc/amq-js-demo`

You will see a message every 10 seconds with the following text:

``Message received: {"id":1,"text":"Hello World!","timestamp":1605814628546}``

This message is been sent and received to the ``example`` queue by the application you just deployed.

# Getting the most from AWS Lambda, monitoring edition

Speaker: Matt Williams from DataDog -- @technovangelist

Talk is about monitoring and lambda

## Overview

* Learn basics of Lambda
* Add AWS lambda to current infra
* Get Monitoring 101
* How to monitor lambda

## What is lambda

* Next progression in the line of app building

Physical Boxes -> Virtual Machines -> AWS instances -> Containers -> Lambda

Lambda makes it easy to run your code and not really worry about where
it executes. Lambda == magic. :-)

* Lambda is your executable code
* Very few restrictions
* Priced based on execution time, quantity, and memory

## Lambda concepts

* Lambda is all about triggers: "events"
* Lambda functions are stateless
* They are without hardware to you, amazon handles this for you
* They can run concurrently (take away -- other talk said it was parallelism...)

## What triggers lambda

* S3
* Kinesis
* Iot devices
* Streams
* Files
* CloudWatch
* DynamoDB
* Amazon API Gateway
* The Echo (Alexa)

## Lambda examples

* Goad -- golang load tester
* Benchling -- http://benchling.engineering/crispr-aws-lambda
* Skills for Amazon Echo
* Chat Bots
* S3 Data Loading
* Bittorrent tracker

## Best practices for lambda

* Write stateless code
* Permission are set correctly
* Local vars only in your code
* Minimize the startup
* Monitor
* Delete old functions

## Adding lambda to my infrastructure

1. Write the code
2. Setup AWS
3. Debug -- rely on log files for information

Can use lambda templates to get a base lambda started.

Events are based on the medium sending to lambda

## Frameworks for lambda

* APEX
* Server Less
* Node lambda (for node)
* Sparta (golang for lambdas)

## Native Gotchas

* Lambda runs on amazon linux container
* Native NPM modules are problematic

## Monitoring 101

* Collect all the data -- it's cheap
* Not having data when you need it is expensive to do it later
* Look at the monitoring 101: Alerting on what matters -- data dog blog posts
* three buckets to look at
  * Work metrics -- Through put, error message e.g. number of 404s
  * Resource metrics -- Utilization, saturation, CPU
  * Events -- code change, alerts, scaling events

## Monitoring AWS lambda stuff

Three options:

* Custom metric created on cloud watch
* Add metric directly to monitoring application -- maybe don't do this
* Add a line to the cloud watch logs -- simple, kind of easy

Data dog just sends a log to cloud watch to let you see what's happening

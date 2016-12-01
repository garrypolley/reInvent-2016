# Solve common problems

Speakers: Sean Senior and Chris Rec

Talk is about solving common business problems in 5 minutes or less
using AWS.

## What to expect

* introduce the builder team
* solutions catalog
* tenets and best practices
* sharing lessons learned
* Walk away with ready to use solutions

## Solution builder team

* Give architecture recommendations
* Packages solutions
* Automating the platform
* Product recommendations
* instance selection for  workloads

## AWS Answers

* Gives best practices
* Strategic guidance
* Has lots of good ready to go solutions you can click and launch
* Turn key ready
* You get to see the architecture overview and step-by-step stuff

## Tenets for their solutions

* Solutions are automated
* They get you up and running fast
* [Well-Architected](https://aws.amazon.com/blogs/aws/are-you-well-architected/) -- secure, performance efficient, reliable, and cost optimized


## Scheduling Solutions

* Limit monitor
* EBS snapshot scheduler
* EC2 Scheduler
  * For turning off dev and test environments
  * Uses lambda functions to turn off and on based on your set schedule

## Networking Solutions

* VPN monitor
* ClassicLink Mirror
* AWS WAF security automation
* Global transit VPC


## Management solutions

* Cost optimization: EC2 right-sizing
* Cost optimization: Monitoring
* Account Management
* Deployment pipeline for IIS on Windows Server
* Centralized logging solution -- comes with visualizations out of the box to help

## Big data solutions

* Real-time analytics with Spark Streaming
* Streaming analytics pipeline
* [Data lake solution][https://github.com/awslabs/aws-data-lake-solution] -- makes it easier for random data needs and is serverless and turn key

Look into Amazon Kinesis Analytics for analyzing data we get in  our system.

They also have partner products like Chef and Puppet ready to go turn key style.

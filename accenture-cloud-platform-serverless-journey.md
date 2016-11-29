# Serverless journey

Speakes: Missed their names -- from Accenture

Excenture is the one making the platform

## What makes a platform

 A platform takes two different groups together and enables them
 to work with eachother.

## How does ACP support ecosystem

 * They are a set of APIs in the middle of stuff happening
 * They are basically a middle man

## Why do Serverless?

* Easier micro services
* AWS has really good serverless stuff
* API gateway makes it easier

## API model

* Has rings
* 0, 1, 2 levels.  Each depending on the one below (it's transitive)
* Doing Accenture DNS to Route 53 DNS makes it easier to move endpoints
* CloudFront and S3 are used to serve single page apps
* API Gateway is used to send requests on to lambda
  * Redis is used to communiate between them
  * Kinesis is used to share streams
  * Also may use sns notify to share between lambdas
* Persistent storage:
  * Elastic search
  * DynamoDb
  * Redshift
* Use cloud watch for logs

## Continuous integration

* Uses TerraForm + Apex to manage infrastructure
* Platform for deploying is built largely in Python (because it's the best)
* Accenture DevOps platform: https://github.com/Accenture/adop-docker-compose
* Platform: http://accenture.github.io/adop-docker-compose/

## Recommendation

* Recommends picking a lambda runtime for all
* Plan for upgrades early
* Have security in mind and defined upfront
* Have logging modeled upfront
* basically plan the system up front

## Patterns

* Make all lambda functions as parrellizable functions
* Cache states if you can
* (I missed the others because I was typing a chat...)

## Operations and Monitoring

* Logs from lambdas can go to Kinesis
* Another lambda can then feed the logs to another source
* Another lambda can then feed the logs for alerting
* Basically by using the lambdas and kinesis you can easily stream/send logs


## Future of serverless application

* Currently some overuse of lambda
* Ideal is to go to a framework to manage resources
* Use the other AWS platform services to supplement the logic in the lambdas
* Need to have a reference model for the ideal architecture (maybe look into the serverless framework -- seems to be a real name for a framework)
* If it's not business logic it does not belong in the lambda

## Using lambda

* Don't use it when something else already exists in AWS land
* Use velocity templates to transform data at the API Gateway level
* If lots of data ingestion is needed use the kinesis stuff
* Look at the AWs RESTful endpoints for updating stuff
* Only use lambda for business logic
* Use streams where you can to optimize throughput
* Don't use cloud watch for real metrics
* Something like Prometheus is good for timeseries based metrics

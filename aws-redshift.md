# Redshift talk

I was 10 minutes late due to long walk.

## Helpful stuff

* Use a logical cross table key for joins
* Column compression encoding may help (need to tst to see how it can help, and which one to use)

## Concurrency optimizations in WLM

* Look at https://github.com/awslabs/amazon-reshift-utils
* Should have queue_seconds in a query down to 0 here
* Performance of sequential small batches is faster/better for their uses cases

## Faster redshift

* Make as few I/O calls as possible
* `select * from table` bad news bears -- "should be illegal"
* Can have data compression per column for each column type
* System will do samples to determine which compression is the best one
* Zone maps make it easier to know where data exists on redshift -- each block has metadata that lets it go faster for searching
* Sorted tables can give faster query results
* Compound sort keys -- use the least selective column first for sorting, the sort blocks will be better
* Interleaved sort keys can make searches and sorting faster
  * Must vacuum reindex for interleaved sort keys to work over long time of new data
  * Columns domain should be stable -- otherwise you get a new "others" bucket
* Choose good distribution key to keep parallelism
  * data types of columns must be the same for speed

## Other Redshift

* There exists an AWS Schema conversion tool
  * Will have best sort key
  * Will have best distribution key
  * You can create a Redshift based one
* QuickSight may help to show how RedShift is doing


## What to check

* Have good data hygiene
* Check queues of data over time
* Keep data on your RedShift over time
* Keep stats to ensure RedShift is healthy
* Apparently easier to maintain if you look at these stats regularly
* Optimize for few queries very fast
* Prioritize queries via WLM queue

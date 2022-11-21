# Kinesis Data Firehose
Kinesis Data Firehose doesn't need shards. You can preprocess the data using [[Lambda]] before storing the data in something like [[Redshift]], [[S3]] etc. Lambda is optional.

Firehose does not have data retention. It is used for streaming data straight to storage or some other repository.


## When do you use Firehose
- When you want to collect streaming data easily
- When processing is optional
- Final destination is [[S3]] or some other data store
- Data retention is not important


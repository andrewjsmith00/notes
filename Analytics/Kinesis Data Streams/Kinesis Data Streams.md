# Kinesis Data Streams
Kinesis Data Streams gets data from producers. This is typically JSON but can be any type of data in a data blob.

Once data is produced, Kinesis streams can be used to move the data. This is done by shards. Shards are like containers which hold the data to move. Once data is in a shard, you use a consumer to process the data. Multiple consumers can consume the data from the stream. You can use the consumers to process the data and then move it to storage.

## Shards
Shards are the container to contain the streaming data. A shard is made up of
- Unique partition key for each shard. Each time a request is made to send data in Kinesis, it creates a sequence associated with a shard in the order it's received. The more requests, the more shards. 

Each shard consists of a sequence of data records. These can be ingested at a rate of 1,000 records per second. 
A data record is the data captured with:
- Sequence number
- Partition key
- Data blob (up to 1mb)

Shards are a transient data store where data is held from 24 hours to 7 days.

## Ingesting Data
1. Use the [[Kinesis Producer Libraray]]
	- A library that allows you to write to a Kinesis stream 
2. Use the [[Kinesis Client Library]]
	- Integrated with the KPL to consume and process data from the stream
3. Kinesis API
	- Low level API operations to send data.


## When should you use Kinesis Data Streams
- When data needs to be processed by consumers
- Real time analytics
- Feed into other services in real time
- Some action needs to occur on the data
- Storing data is optional
- Data retention is important
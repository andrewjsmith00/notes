## File mode
Loads all the data from [[S3]] directly into the training volumes. Data is stored in the format they are in [[S3]] such as CSV, JSON, [[Parquet]], etc.

## Pipe mode
The dataset is streamed directly to the instance from [[S3]]. This provides faster start times and better throughput. This uses recordIO-protobuf (creates a tensor). Essentially the tensor is a multi-dimensional array. 



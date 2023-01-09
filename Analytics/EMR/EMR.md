# Amazon EMR
Amazon EMR provides a managed [[Apache Hadoop]] framework. You can run many popular distributed frameworks like [[Apache Spark]], [[Apache Flink]], [[Apache Hive]] and more. You can use it to perform log analysis, web indexing, ETL, [[machine learning]] and more.

EMR offers a rich ecosystem of libraries and other services for [[SQL]], notebooks, processing and more.

When you launch an EMR cluster you need to define compute resources for the master, core and task nodes.

## Master Node
Each cluster has a master node which manages the cluster. It coordinates the distribution of data within the cluster and runs the primary Hadoop daemons such as the name node, job tracker and resource manager

## Core Node
Job tasks are performed on a collection of core nodes. Data is stored using [[Hadoop File System]].

## Task Nodes
Optional
Only run tasks and only run the task tracker daemon.



You can resize an EMR cluster automatically or manually.

## EMR Storage Connectivity
You can connect to many storage locations from EMR such as:
- [[EMR DynamoDB Connector]]
- [[JDBC]]
- [[ElasticSearch]] Connector
- [[EMR File System]]
- Streaming Connectors
- [[Redshift]] copy from HDFS

## EMR Networking
There are various options for networking setups with EMR. In a [[VPC]] you can deploy to a public or private subnet. Public subnets are easier to provision but limited security. This is helpful if the data isn't overly sensitive. With this, you can connect to the various web interfaces of the applications running on EMR.

You can improve security of networking by deploying the cluster in a private subnet. You can configure NAT for outbound traffic and a [[VPC Endpoint]] for private access to [[S3]]. To access the cluster itself you can use a bastion host. You can use a proxy and [[SSH]] tunnel to get access to the web interface for EMR.

You can also use a [[VPN]] to connect to an on-premises network.
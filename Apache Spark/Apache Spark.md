# Apache Spark
Apache Spark is a unified computing engine and libraries for parallel data processing on clusters. It supports many languages such as [[Python]], [[Java]], [[Scala]] and [[R]] and has libraries for [[SQL]], streaming, [[Machine Learning]] and more. It can run anywhere and is easy to scale.

The components and libraries offered are:
![image](https://learning.oreilly.com/api/v2/epubs/urn:orm:book:9781491912201/files/assets/spdg_0101.png)

## Spark's Philosophy
### Unified
Spark's key goal is to be a unified platform for big data applications. It is desgined to support a wide range of data analytics tasks from data loading and SQL to machine learning and streaming over the same engine and set of APIs.

### Computing Engine
Spark limits the scope to a computing engine. This means it handles loading data from storage systems and performing computation on it but not the storage itself. You can use Spark with many persistent storage systems like [[S3]], distributed file systems like [[Apache Hadoop]], key-value stores like [[Apache Cassandra]] and message buses like [[Apache Kafka]]. Spark will not store data long term, or favour one over the other. The key motivation is that data is already in a mix of storage systems and is expensive to move. Therefore Spark focuses on performing computations over the data and works to make these storage systems appear similar.

Spark's focus on computation makes it different from earlier big data software platforms like [[Apache Hadoop]]. Hadoop includes a storage system, [[Hadoop File System]], which is designed for low-cost storage over a cluster, and a computing system [[MapReduce]], which were closely integrated. This choice makes it difficult to run without the other and makes it a challenge to write applications that access data eleswhere. Spark runs well on Hadoop storage but is used where the Hadoop architecture doesn't make sense like the cloud or in streaming.

### Libraries
Spark's final component is the libraries which build on its unified design to provide a unified API for common tasks. Spark supports a standard library and an array of external libraries with the standard library being the bulk of the project. Spark libraries include SQL ([[Spark SQL]]), machine learning ([[MLlib]]), stream processing ([[Spark Streaming]] and [[Structured Streaming]]) and graph analytics ([[GraphX]])
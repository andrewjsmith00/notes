# The SparkSession
The SparkSession is what controls the [[Spark Applications]]. It is the way Spark executes user-defined manipulations across the cluster. There is a one-to-one correspondence between a SparkSession and a Spark Application. In [[Scala]] and [[Python]], the variable is available as `spark` when starting the console.

To do something such as creating a range of numbers, you can do something like:
```python
myRange = spark.range(1000).toDF("number")
```

```scala
val myRange = spark.range(1000).toDF("number")
```
This range of numbers is an instance of [[DataFrames]]. It was created with one column of 1,000 rows with values from 0 to 999. When this is run on a cluster, each part of this range of numbers exists on a different executor.
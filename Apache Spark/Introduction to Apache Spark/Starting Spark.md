# Starting Spark
When writing [[Spark Applications]] you need a way to send user commands and data to it. You do this by creating a [[SparkSession]].

When starting Spark in interactive mode, it will implicity create a [[SparkSession]] to manage the [[Spark Applications]]. When creating a standalone app, you need to create the SparkSession
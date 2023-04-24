# Spark's Language APIs
The Spark language APIs let you run code using various languages. Mostly, Spark presents some core 'concepts' in each language which are then translated into Spark code which runs on the machines. If you just use the Structured APIs, all languages will have similar performance characteristics. Here's a rundown:

[[Scala]]
	Spark is written primarily in Scala, making it the 'default language'.

[[Java]]
	The authors of Spark have worked to ensure you can write Spark code in Java

[[Python]]
	Python supports almost all constructs that Scala supports. See [[PySpark]]

[[SQL]]
	Spark supports a subset of the ANSI SQL 2003 standard, making it easy for analysts and non-programmers to use Spark

[[R]]
	Spark has 2 common R libraries, one is part of Spark core ([[SparkR]]) and one is community-driven ([[sparklyr]])

![image](https://learning.oreilly.com/api/v2/epubs/urn:orm:book:9781491912201/files/assets/spdg_0202.png)

Above is the relationship between the [[SparkSession]] and the language APIs. Each language API maintains the same core concepts. There is a [[SparkSession]] that is available to the user, which becomes the entrance to running Spark code. When using Spark from Python or R, you don't write [[JVM]] code, instead you write native code that Spark will translate into code that can be run on executor JVMs.
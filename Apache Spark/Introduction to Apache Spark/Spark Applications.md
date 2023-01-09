# Spark Applications
Spark Applications have a *driver* process and a set of *executor* processes. The driver process will run the `main()` function, sits in a node in the cluster and is responsible for:
- Maintaining information about the Spark Application
- Responding to a user's program or input
- Analysing, distributing and scheduling work across executors

The driver process is essential. It is the heart of the application and maintains all relevant information during its lifetime.

The *executors* are what carry out the work that is assigned to them by the driver. Each executor is responsible for two things:
1. Execute assigned code
2. Report status of computation

Below demonstrates how the cluster manager controls the machines and allocates resources to Spark Applications. This means that multiple Spark Applications can be running on a cluster at the same time.
![image](https://learning.oreilly.com/api/v2/epubs/urn:orm:book:9781491912201/files/assets/spdg_0201.png)

Above we can see the driver on the left and four executors on the right. This diagram does not have the concept of cluster nodes. The user can specify how many executors should fall on each node through configurations.

Overall, the key points to understand are:
- Spark employs a cluster manager to keep track of resources
- The driver is responsible for executing the driver program's commands across executors.

The executors will mostly be running Spark code. However, the driver can be driven from a number of languages through [[Spark's language APIs]].
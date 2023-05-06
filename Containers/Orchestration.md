# What is Orchestration?
Container Orchestration refers to processes used to manage containers and to automate the management of containers.

For example:
- I want to start up a set of five containers in production
- I could spin up each individually
- Or I can use an orchestration tool like [[Kubernetes]] and tell it that I want five containers and let the tool do it


Containers allow zero-downtime deployment which goes as follows:
- Spin up containers running the new code
- When they are up, direct user traffic to new containers
- Remove the old containers running old code once there are no users on them

How to do this quickly and efficiently?
Orchestration tools!

Things that are not Kubernetes:
- [[Docker Swarm]]
- [[Marathon]] - Based on [[Apache Mesos]]
- [[Nomad]]
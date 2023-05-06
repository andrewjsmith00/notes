A Pod is the smallest component in [[Kubernetes]].
A Pod is a group of one or more [[Containers]] and share storage, network resources and a specification for how to run the containers.

The shared context of a Pod is a set of [[Namespaces]], [[cgroups]] and other components of isolation.

In order to run the container, Kubernetes will schedule a pod to run on servers in the cluster. When a pod is scheduled, it runs the containers that make up the pod.
# Networking in Kubernetes
The [[Kubernetes]] networking model creates a virtual network across the nodes in the cluster. It means that every pod has its own IP address and can communicate with the other pods in the cluster regardless of the node they are running on.

Kubernetes supports many networking plugins implementing the networking model in many ways. One of which is [[Flannel]]


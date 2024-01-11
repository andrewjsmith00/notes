The [[Kubernetes]] Cluster Autoscaler adjusts the size of a cluster so all [[Pod]]s can somewhere without unneeded nodes. This scaling happens when:
1. There are pods that fail due to insufficient resources
2. There are [[Worker Node]]s in a cluster that are under-utilised and the [[Pod]]s can be placed elsewhere

When using the Autoscaler for AWS, [[Kubernetes]] will configure the [[EC2 Autoscaling]] Group of the [[Managed Node Group]] to scale nodes
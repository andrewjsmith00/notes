The worker node in [[Kubernetes]] is the system that runs the containers in the cluster. The [[Kubernetes Control Plane]] manages these nodes.

These nodes have a few elements:
- [[kubelet]] - Provides the API for interacting with the node
- [[kube-proxy]] - Sets up the virtual network via [[IPtables]] rules
- The container runtime which pulls and runs containers. Examples include:
	- [[Docker]]
	- [[containerd]]
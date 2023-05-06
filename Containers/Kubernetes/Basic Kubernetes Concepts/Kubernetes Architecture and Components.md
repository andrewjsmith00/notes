# Kubernetes Architecture and Components.
[[Kubernetes]] includes multiple components that work together to provide the functionality of the cluster.

The control plane parts manage and control the cluster.
- etcd: Provides distributed synchronised data storage for the cluster
- kube-apiserver: Serves the Kubernetes API which is the primary interface of the cluster
- kube-controller-manager: Bundles several components into one package
- kube-scheduler: Schedules pods to run on individual nodes

In addition to the control plane, each node also has:
- kubelet: Agent that executes containers on each node
- kube-proxy: Handles network communication between nodes by adding firewall routing rules.

With kubeadm, many of these components run as pods in the cluster.
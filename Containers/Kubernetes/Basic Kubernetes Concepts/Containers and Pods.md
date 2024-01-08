[[Pod]]s are the smallest and most basic building block of [[Kubernetes]]
A pod will have one or more [[Containers]], storage and IP address in the Kubernetes network

In order to run containers, Kubernetes will schedule pods to run on servers in the cluster. When a pod is scheduled, the server will run the containers that are part of that pod

An example of a pod running [[NGINX]] is
```shell
cat << EOF | kubectl create -f -
apiVersion: v1
kind: Pod
metadata:
	name: nginx
spec:
	containers:
		- name: nginx
		  image: nginx
EOF
```

`kubectl get pods --all-namespaces`

`-n` means namespace

You can use `kubectl describe pod $pod_name` to see more information about a pod such as the event log and more


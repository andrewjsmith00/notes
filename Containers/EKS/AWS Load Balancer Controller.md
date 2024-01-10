The AWS Load Balancer Controller is a [[Controller]] that manages [[Elastic Load Balancer]]s in a [[Kubernetes]] cluster.

It can provision an:
- [[Application Load Balancer]] for a [[Kubernetes Ingress]]
- [[Network Load Balancer]] for a Kubernetes [[Service]] of type [[LoadBalancer]]

You can configure your load balancer controller to act in Instance Mode or IP Mode


## Instance Mode
This registers each [[Worker Node]] as a load balancer target. When the request is received they forward the request to the appropriate [[Pod]] using [[kube-proxy]].

## IP Mode
[[EKS]] gives [[Pod]]s a dedicated IP address. IP mode will use the IP of the [[Pod]] as the target where the request is forwarded to.
Ingress is a [[Kubernetes]] API resource which allows for the management of internal or external HTTP(S) access to Kubernetes [[Service]]s running in a cluster.

One way of managing this is via [[Application Load Balancer]]s which load balance at layer 7 of the OSI model and support [[TLS]], [[WebSocket]]s, [[WAF]] and other resources.

You can use multiple Ingress objects in the same cluster. Typically this will create a separate ALB but the [[IngressGroup]] allows for multiple Ingress resources to be grouped. This [[Controller]] will automatically merge Ingress rules and put them on the same ALB.

This requires an annotation `alb.ingress.kubernetes.io/group.name` which then groups by group name.
EKS is a managed offering of [[Kubernetes]]. It manages the control plane for you which includes [[etcd]], the API server. This runs in an AWS controlled [[VPC]].

The data plane runs in your [[VPC]]. This can run on [[EC2]]. Here you have to think about the [[AMI]] and register them with the control plane. An easier way to do this is to use [[Managed Node Group]]s which handle the provisioning and lifecycle of the compute nodes. The [[Managed Node Group]]s use [[EC2 Autoscaling]]. [[Fargate]] is also supported for serverless compute.


EKS also runs using [[EKS Outputs]] and [[EKS Anywhere]].

EKS is Kubernetes Conformant meaning it works cloud-agnostic.
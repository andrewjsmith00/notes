[[Route 53]] can be set up in an architecture to integrate in a [[Hybrid Network]] where requests from within AWS are resolved using the On-premise network [[DNS]] resolver using [[Route 53 Resolver Rules]] and [[Route 53 Resolver Endpoints]]. Resources in a [[VPC]] can reach out to [[Route 53]] for DNS which forwards the request over a [[Transit Gateway]] and [[Direct Connect]]


Reference: https://docs.aws.amazon.com/prescriptive-guidance/latest/patterns/set-up-dns-resolution-for-hybrid-networks-in-a-multi-account-aws-environment.html

#sap 
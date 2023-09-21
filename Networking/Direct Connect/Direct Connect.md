Direct Connect is a service that allows you to connect directly to AWS from your on premises data centre using a Direct Connect location.

In your data centre you provision a [[Customer Gateway]] which has [[BGP Routing]]. In your account you create a [[Direct Connect Gateway]] which connects to a [[VPC]] or [[Transit Gateway]].


If you have multiple data centres connected via Direct Connect, you can use [[SiteLink]] to establish a connection between the two via AWS which can be used as a redundant link if the direct line between two data centres goes down.
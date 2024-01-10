DNS resolution in [[Kubernetes]] works as a combination of the [[Service]] and the [[Namespace]].

This ends up appearing as `<service>.<namespace>.svc.cluster.local`

If I have a service called `data` in a [[Namespace]] called `prod`, the DNS can be formed as:
`data.prod.svc.cluster.local`
which can be abbreviated to:
`data.prod`
from outside the `prod` [[Namespace]] in the cluster.
Inside the [[Namespace]] it works as:
`data`


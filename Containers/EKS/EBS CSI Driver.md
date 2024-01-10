The [[EBS]] [[Container Storage Interface]] Driver allows for [[EKS]] clusters to manage [[EBS]] volumes as storage.

These need to be managed as an [[EKS Add-On]] which can be done as below:

```bash
aws eks create-addon —cluster-name $EKS_CLUSTER_NAME —addon-name aws-ebs-csi-driver —service-account-role-arn $EBS_CSI_ADDON_ROLE
```

Once this is active, it creates a [[DaemonSet]] which runs on a [[Pod]] in each [[Worker Node]] in the cluster. It also configures the [[StorageClass]] object
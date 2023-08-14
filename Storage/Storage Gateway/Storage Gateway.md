Storage Gateway is a service which can be used to act as a gateway between [[S3]] and an on-premises machine. It is useful when migrating data to cloud.

It has 4 modes where the file system is available under either [[NFS]], [[SMB]] or [[iSCSI]].
These modes can either act as a direct link to [[S3]], perform asynchronous replication to [[S3]], use [[S3]] as the primary data store with commonly accessed files cached locally or act as a virtual tape library for backups.
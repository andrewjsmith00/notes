[[RDS]] has 2 methods of replication, synchronous replication and asynchronous replication. 

## Synchronous Replication
Synchronous replication is used for [[Standby Instance]]s where for each write committed on the master, it is instantly replicated to the standby.

## Asynchronous Replication
Asynchronous replication is used for [[Read Replicas]] which can be contained in other AZ or region. This can have some delay between when it happened on the master.
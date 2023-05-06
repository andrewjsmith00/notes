# [[S3]] Object Lock and [[Storage Classes#Glacier]] Vault Lock
## [[S3]] Object Lock
You can use [[S3]] Object Lock to store objects using a write one, read many, (WORM) model. It can prevent objects from being deleted or modified for a fixed amount of time or indefinitely. You can use it to meet regulatory requirements that require WORM Storage or add an extra layer of protection against object changes and deletion

### Governance Mode
Users can't overwrite or delete an object version or alter its lock settings unless they have special permissions.
With governance mode, you protect objects against being deleted by most users, but you can still grant some users permission to alter the retention settings or delete the object if necessary.

### Compliance Mode
A protected object version can't be overwritten or deleted by any user, including the root user in your AWS account. When an object is locked in compliance mode, its retention mode can't be changed and its retention period can't be shortened. Compliance mode ensures an object version can't be overwritten or deleted for the duration of the retention period.


## Glacier Vault Lock
Allows you to easily deploy and enforce compliance controls for individual [[S3]] Glacier vaults with a vauilt lock polocy. You can specify controls such as WORM in a vault lock policy and lock the policy from future edits. Once locked, the policy cannot be changed.

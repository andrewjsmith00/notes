# [[Organizations]] Organizational Units
## Operations on organizational units (OUs)
### Managing OUs
OUs group accounts to create hierarchies that organise accounts into a system. While this may appear trivial, this allows customers to more easily create a hierarchy of their multiple accounts. When they need to apply a service control policy(SCP), it will only affect the necessary accounts.

The number of levels deep that an OU can be nested is dependent upon the policy types enabled for that root. For service control policies, the limit is five.
### Creating OUs
The [[Organizations]] API `CreateOrganizationalUnit` creates an organizational unit within the root of the organization (at the top of the organization) not nested within an existing OU, or within an existing OU by specifying the unique ID. VAL_1 is the unique ID of the parent root or OU.

To retrieve the root ID, use the [[Organizations]] API ListRoots. To retrieve the parent OU ID, use the [[Organizations]] API `ListORganizationalUnitsForParent`. VAL_2 is the friendly name assigned to the new OU.
### Moving member accounts to OUs
### Removing OUs

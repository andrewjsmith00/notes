# Permanent [[IAM]] Credentials
## Building Blocks
### Users
Physical person. 1 user = 1 person

### Groups
Job functions. Admin, dev, etc. Contains users

### Roles
Internal usage within AWS



It is best practice for users to inherit permissions from groups. This way permission changes are done at a group level rather than having to change individually for every group.


**Principle of Least Privilege**
Only give people the minimum access they need to do their job


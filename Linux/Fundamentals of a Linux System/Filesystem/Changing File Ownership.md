# Changing File Ownership
Ownership is changed using the `chown` and `chgrp` command for the owner user and owner group respectively. The user must be the owner of the file or a member of the group that they wish to change group ownership to. The `-R` switch will do this recursively.

Syntax is as follows:
`chown user /path/to/file`

Chown can also be used to change the user and the group ownership in one go:
`chown user:group /path/to/file`

Using globing with `chown` is not recommended as it may match undesired files. For example `chown johndoe .*` to change all hidden files' owner in the current directory will also match the `.` and `..` effectively changing the ownership of the current and parent directories. Instead use the find command: `find . -type f -name ".*" | xargs chown johndoe`

## Setting default permissions (`umask`)
The `umask` command is used to set the default permissions that files and directories are granted when they get created. Every process has its own `umask` value that influences the file permissions that the user creates in their session. The `umask` works by subtracting permissions. That is it specifies which permissions that you don't want granted. 

## Access Control Lists (ACL)
The traditional permission model for [[Linux]] has some shortcomings. For example, if you want a user that is not in a group to read a file that is created, yet you don't want the file to be word readable just to let that user have the required access? This is why ACLs were introduced.

They are supported by the filesystem so they must be turned on while mounting by using the `-o acl` as a mount option. ACL deals only with the nine permission bits of files. `setuid`, `setgid` and `sticky bit` are not implemented here.

The syntax of setting ACL is as follows:
`setfacl user:username:permissions`
For example: `setfacl -m u:johndoe:r /path/to/file`
Or `setfacl -m g:admin:rx /path/to/file`

You can use the `-R` switch to make recursive permission changes. To viewthe ACL of a file or directory, use `getfacl /path/to/file`
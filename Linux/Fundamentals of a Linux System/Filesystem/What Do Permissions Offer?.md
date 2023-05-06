# What Do Permissions Offer?
For a file, a read permission means that this file can be read and copied. The write permission means that the file can be modified. The execute permission allows the file to be executed directly (binary files) or by an interpreter (Python, BASH, etc.)

The read permission on a directory allows it to be listed for its files. It alone will not allow directory access. The write permission allows the directory to be modified. That is, file creation, deletion and renaming. Execute permissions allows the directory to be accessed, but you cannot list files. As such, directories are set with read and execute permissions.

## Other file attribute bits
The remaining three bits of file attributes are:
4000 and 2000 represent the `setuid` and `setgid` bits. When set on executable files, they are run in the account ID of the owner user or group rather than the context of the user who executed them.
When `setgid` bit is added to a directory, all new files created under it become owned by the owner group of the directory instead of the owner group of the user who created it. this is useful in directories used by multiple users.

1000 represents the `sticky bit`. When this is set on a directory, you cannot delete or rename a file inside unless you are the owner of the directory, the file or you are the superuser. This is typically the case with the `/tmp` directory, where anyone should be allowed to create files, but only the owner of the file can change or delete it.

Setting the remaining three bits using `chmod` is done the same way as standard permissions.
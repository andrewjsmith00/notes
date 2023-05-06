# File Deletion with `rm`
You can use the `rm` command to delete all types of files. 

If you want to delete an empty directory, use `rmdir`, to delete a directory with files use `rm -r`. 

The `rm` command will ask the user for confirmation before deletion by default. This can be overridden with the `-f` argument.

Deleting files/directories that have special characters can be done by using the `--` switch (everything after -- is treated literally). You can also quote the filename with double quotes or use globing. If you use globing you should use the `-i` switch.

## File Aspects
In [[Linux]], a file will have nine bits controlling the read, write and execute permissions. In addition, there are also three bits that control how the file will get executed, called 'mode' bits.

A file also contains four bits defining the type. These cannot be changed.

The `chmod` command can be used to change the 12 bits of permissions if used by the file owner or superuser.

You can view file permissions using the `-l` switch of `ls` with `ls -l` for files and `ls -ld` for directories. File permission bits are in the order of owner user, owner group and everyone.

The numbers are in octal.
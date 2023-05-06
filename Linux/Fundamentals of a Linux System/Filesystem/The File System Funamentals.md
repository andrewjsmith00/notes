# The File System Fundamentals
## What is a filesystem?
A representation fo storage and the other objects on the system. With [[Linux]], everything is a file: regular file, devices, drivers and processes.

The kernel provides an abstract layer for dealing with different filesystem consistently. For example, you work with files on the local machine as well as CIFS and NFS the same way.

Popular filesystems are:
- ext3 and ext4 for Linux
- ZFS for Solaris (can also be used in Linux)
- JFS for AIX
- Iso9660 for DVD (and mounting ISOs)

## File names and paths
Any Linux filesystem starts at `/`. As you go deeper, more directories get added to root until the desired file is reached. For example `/var/log/jupyter.log`.

You can access a file by using an absolute path (starting at `/`) or relatively (starting at the current directory). 

The Linux kernel poses some limitations when dealing with pathnames on the shell, both of which are considerably high enough as to never be reached:
- Each segment in the path should not be more than 255 characters
- The whole path length cannot exceed 4095 bytes

Filenames that contain spaces can be represented either quoted with double quotes or have the space escaped by `\`


## Mount points
A device has to me mounted in order to be accessed by the system. The syntax to mount is:
``` bash
mount /path/to/device /mountpoint
```

Mount points are stored in `/etc/fstab`. This allows the system to run `fsck` on the filesystems when booting, and to mount devices found in this file automatically on startup.

You can detach (unmount) a filesystem using the `umount` command. There must not be any processes that use the filesystem to be successfully unmounted. The `-l` argument can be added to `umount` to perform a lazy unmount. That will remove the mount point from the directory tree but the device will not be completely unmounted untill all processes using the device have exited. The `-f` is natively available but it cannot be used on modern filesystems like ext3 and ext4 as they are journaled filesystems. These filesystems keep a journal of files created, etc. to be able to recover in the event of a failure.
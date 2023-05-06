# Important Directories
## Important directories on your filesystem
The following are the most important system directories:
	`/etc` has sensitive config files
	`/bin` system utilities and commands like `ls`, `cat`
	`/sbin` commands that are intended to be run as superuser like `mount` and `mkfs`
	`/dev` device files, like disks
	`/lib` and `/usr/lib`: shared libraries. Often `/lib` has symbolic links to `/usr/lib` to facilitate the updating of a library without breaking dependent applications
	`/usr`: contains various programs and libraries. Also has the `man` pages
	`/var`: contains vvariable files (files that change alot) like logs and spool directories
	`/home` not strictly a system directory. It is the location where the users' home directories are placed

## How does Linux view files?
[[Linux]] can recognise only 7 types of file regardless of if its a real physical file, a device or virtual file:

### Regular
The most common file type. These contain streams of bytes with no special order. can be text files, binary executables, images and audio files are all examples of regular files.

Regular files can be accessed sequentially and randomly. Sequential access means that the file is being accessed a certain group of bytes at a time, in sequence. Random (direct) access means that you can jump to any point in the file and start reading from this point forward or backward.

### Directories and hardlinks
Directories contain pointers to files inside them. File information are stored in the directory and not in the files themselves. That is why you must have write permission on a given directory to be able to delete files underneath it. Otherwise you can't delete a file even if you have full permissions.

A directory can have more than one reference to the same file. These are called *hard links*. A hard link of a file is treated just the same as the original file. It cannot be created on other filesystems.

A hardlink can be created using the `ln` command and deleted with `rm`

You can delete a directory using the `rm -r` or `rmdir` commands

### Device files
Device files are used as a means of communications between the system and the physical hardware device.

Device files receive requests from the kernel and redirects it to the device driver which sends it to the physcal device and vice versa.

If the device file is a character one, buffering is done by the device driver. Character device files are used with devices that do not need to transfer large amounts of data. Character device files are denoted by `c` in `ls -l`. Examples are things such as `tty`

Block devices rely on the kernel to do the buffering. They deal with data in large chunks. Block devices are denoted by `b` in `ls -l`. Examples are things such as disks

### UNIX domain sockets

### Named pipes

### Symbolic links
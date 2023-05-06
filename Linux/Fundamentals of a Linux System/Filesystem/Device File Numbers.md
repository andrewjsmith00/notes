# Device File Numbers
Device files have a major and minor number. The major number informs the kernel about the physical location of the device on the system. For example, 8 as a major number represents a disk device. The minor number is interpreted by the device driver itself. For example 1 in `/dev/sda1` represents disk partition 1.

The `udevd` daemon is responsible for discovering new devices and assigning device numbers to their files. It also deletes them according to kernel notifications of hardware changes.

## UNIX domain sockets
These represent ways to allow processes to connect to each other on the same system. Do not confuse them with network sockets. These are inter-process connections on the same machine that do not involve networking.

They appear like files but they cannot be accessed except from the connected processes. A prominent example of a process using UNIX sockets is the `syslogd` daemon which collects system logs.

You can view a socket file by navigating to a process directory that uses a socket in `/proc/PID/fd`

## Named pipes
Created by user.
They service the same purpose of UNIX sockets: connecting processes. You can think of a named pipe as a shell pipe `|` but it is bidirectional. They are also referred to as FIFO pipes.

Use the `mkfifo` command to create them (or `mknod`). Once created you can view it on the filesystem like any other file.

An example of using named pipes is to share terminal windows:
1. In the first terminal, create a pipe using `mkfifo pipe`
2. Then instruct the terminal to redirect the output to the pipe using the script command `script -f pipe`
3. On the second terminal, `cat` the pipe `cat pipe`
4. Now everything you type or see on the first terminal is automatically in the second one

## Symbolic Links
Shortcuts to files and directories, Also called softlinks to differentiate from hard links. They are not direct references to files. Created via `ln -s`

They can cross filesystem boundaries (unlike hardlinks).

A prominent use of symbolic links is in the `/lib` and `/usr/lib` directories, they contain symbolic links with general library names (without the version. This allows library files with general library names (without the version) to be uodated with new ones without breaking the applications that are currently using them, as those applications point to the general library name.

Can be deleted with `rm`
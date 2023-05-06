# Killing a Zombie
A zombie is a leftover bit of a dead process that hasn't been cleaned up properly. This process has completed execution through the `exit()` system call, but it is still in the process table.

Normally, after the child uses `exit()`, the parent receives a `sigchld` signal, which triggers the parent to issue the `wait()` system call which should clean up all zombies. One the parent has read the exit status via the `wait()` system call, the zombie is 'reaped'.

Zombies occur naturally, and on most cases disappear naturally as well. The switch between the `exit()` system call from the zombie and the `wait()` system call by the parent is normally very fast.


## Removing Zombies
Zombies do not use system resources. Only a PID which is a limited amount. If you only have a limited amount of zombies it is best to do nothing. Alternatively, sending `SIGCHLD` to the ppid (parent PID) may help:
`kill -s SIGCLD <ppid>`

Or you can kill the parent process which fails to do what it should be doing and doesn't clean up the zombies. If you kill the parent process it will become a child of `init` which occasionally issues the `wait()` system call.
Alternatively you can reboot.

## About Orphans
An orphan process is a process without a parent.
Orphan processes get PID 1 as the new parent
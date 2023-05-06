# Understanding how a process is created
## How processes are created
### `fork()` and `exec()`
`fork()` is a system call where a process makes a copy of itself to create a child process. Next the child process will call the `exec()` system call to overlay itself with the other program.

While a `fork()` is happening, the child process will create address pointers in a virtual memory to the same physical memory pages as the parent process. If either process changes their variables it will only be visible locally.

When the child is created, it will receive a PID (process ID), using the `getpid()` system call.

When the child is terminated, the parent gets back the child PID.

`exec()` is an alternative to `fork()`. In `exec()`, the parent code is replaced with the child code and the parent ceases to exist.

When a process reaches the end of its life it sends `exit()` and then the parent is responsible for the cleanup.
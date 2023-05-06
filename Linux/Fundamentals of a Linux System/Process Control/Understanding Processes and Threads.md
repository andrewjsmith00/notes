# Understanding Processes and Threads
## Processes and Threads
Processes that are multi-threaded can do more efficient multitasking as the threads can run in parallel on multiple CPUs

If a system only has one CPU, Linux will use time slicing. This is where every process or thread is getting its part of CPU time. To do this, the CPU will use context switching. This is where it will switch processes to appear as if it is multitasking.

Context switching allows for multi-tasking, but it comes with its disadvantages. Every time the CPU switches to a different process, the cache needs to be rebuilt and that is a slow process. To optimise this process it is a good idea to pin processes to specific CPUs. You can do that with cgroups and systemd.

`taskset` lets you choose the CPU a process uses.
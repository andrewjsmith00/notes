# Memory Management
When an application requests memory to operate, the kernel will offer this memory in the form of 'pages'. In [[Linux]], a page size if 4 KiB

The kernel serves those pages from physical storage hardware (either RAM or SWAP space)

The kernel shuffles pages between the SWAP space and with RAM. Memory that does not get accessed for a while gets moved to SWAP space to allow for more free space

As more processes demand memory, the kernel will fulfil these requests by paging in and out pages with the SWAP space. As the disk is the slowest component this will degrade performance.

If the system runs out of memory and SWAP, the kernel will kill the least important processes with an 'out of memory' kill function. Try to avoid this.

`swapon -s` shows the SWAP space.

## Using `vmstat` to measure memory performance
`si` -- swap in
`so` -- swap out

## Disk IO measurement and analysis
Disk IO is measuring using `iostat` command. It is used the same way as `vmstat`. You can add `-d` to make the output specific to disk performance. `-x` is used for extended statistics.

You should take note of:
- `svctm` : average service time spent serving IO requests
- `%util`: percentage of CPU cycles spent during IO requests being issued
- `r/s` and `w/s`: reads and writes per second

If any of these are high for a long period it means the disk is causing a bottleneck and you should upgrade the drive or distribute load with something like RAID.


## Optimising disk IO with 'scheduler'
The IO scheduler is a kernel module that organises and controls processes' access to the disks and their IO requests. There are 3 options:
- CFQ: Completely Fair Queuing. Default and recommended for general purpsoe. Distributes load evenly and has balance between throughput and latency
- Deadline: Caps maximum latency for an IO requests and provides the max possible throughput. Best for disk-intensive apps like databases
- NOOP: Uses FIFO to handle IO. Assumes that performance has been optimised by the disk controller. Suited to SSDs

You can change the default IO scheduler at boot by editing `/etc/grub.conf` and adding `elevator=*option*` at the end of the kernel line.

You can change this dynamically as well by echoing the algorithm name to `/sys/block/<device>/queue/scheduler`

## Slow system quick diagnosis and remedy
If you find the system running slower than before and users start to complain, examine the resources to find bottlenecks.

For example, run `ps auxwww` to find CPU utilisation per process. If a process is using more than 50% for a long time this can indicate that the process is at fault. Check load average with uptime to determine whether the CPU is contended

Check paging with `vmstat`. If there is a lot of page-outs then the physical memory is overloaded. If there is a lot of disk activity without paging then a process is using the disk alot. If this is not intended then inspect the process

It is difficult to know exactly which process is using the disk the most but `kill -STOP` will temporarily suspend the susceptible process

If a process is resource intensive you can do many things. you can use `renice` if it is CPU intensive to decrease its priority or you can ask the user to run it later. IF the process is using a lot of network or disk you can tune the process itself.
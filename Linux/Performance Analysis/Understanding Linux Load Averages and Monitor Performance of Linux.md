# Understanding Linux Load Averages and Monitor Performance of Linux
The Linux load average is believed to be a running average of processes in execution queue tagged as running or interruptible.
```shell
$ uptime

07:13:53 up 8 days, 19 min,  1 user,  load average: 1.98, 2.15, 2.21
```
This means:
- 1 minute load average is 1.98
- 5 minute load average is 2.15
- 15 minute load average is 2.21

High load averages imply the system is overloaded and many processes are waiting for CPU time.

You can also read the `/proc/loadavg` file to get the load average.

## Understanding System Average Load In Relation to the Number of CPUs
To understand the system load/performance you need to understand number of CPU cores of performance.

### Multi-processor vs multi-core
Multi-processor: Two or more physical CPUs
Multi-core: CPU has two or more cores

`nproc` or `lscpu` will show the number of processing units.

With the following system load:
`23:16:49 up  10:49,  5 user,  load average: 1.00, 0.40, 3.35`

On a single core this means:
- CPU was fully utilised on average. One process was running on the CPU over the last 1 minute
- CPU was idle by 60% on average. No processes were waiting for CPU time over the last 5 minutes
- CPU was overloaded by 235% on average. 2.35 processes were waiting for CPU time (3.35) over the last 15 minutes.

On a dual core system this means:
- The one CPU was 100% idle on average. One CPU being used and no processes were waiting for CPU time (1.00) over the last 1 minute
- The CPUs were idle by 160% on average. No processes were waiting for CPU time (0.40) over the last 5 minutes
- The CPUs were overloaded by 135% on average. 1.35 processes were waiting for CPU time (3.35) over the last 15 minutes
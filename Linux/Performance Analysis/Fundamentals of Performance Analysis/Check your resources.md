# Check Your Resources
Before addressing a performance degredation problem, you should check your assets to have an upper bound for the system's general performance level.

The following files files provide hardware information:
- `/proc/cpuinfo` has the vendor ID, CPU family, model and model name. Each processor core will have a stanza of its own. Useful information can be extracted from the CPU flags like `ht` which means that the CPU is using hyperthreading
- `/proc/meminfo` has details on total, used and free memory
- `/proc/diskstats` has disk device statistics.

Another useful command for this is `dmidecode` which prints a bunch of hardware information about the machine such as motherboard type, BIOS version, installed memory and more.

## Using `vmstat` to measure CPU utilization
When measuring CPU performance you may want to determine the overall CPU utilisation to know whether or not the overall clock speed is the problem. Load averages may assist with this. In addition, you may want to check per-process CPU consumption to know which processes are really consuming the CPU.

Running `vmstat` gives you the required information. It takes the number of seconds and the number of reports as the first and second arguments to determine the number of seconds for which the tool will calculate the averages. The first line of output represents the averages since the systems boot time. The subsequent lines present the average per n seconds.

The rightmost column is for CPU readings. `us`, `sy`, `id` and `wa` represent the user, system, idle time and wait time for the CPU.

A high `us` means that the system is busy doing computational tasks, while a high `sy` time means that the system is making a lot of system calls and/or making a lot of IO requests. A system should typically be using no more than 50% in user time, no more than 50% in system time and have a non-zero idle time.

The `cs` is short for context switches per interval. That is how many times the kernel switched the running process per interval. The `in` is short for interrupts, it shows the number of interrupts per interval. A high `cs` or `in` rate may mean that there is a malfuntioning hardware device.

## CPU load average and per-process
Using the `uptime` command, it essentially provides the total time spent since the system was booted, but it also offers a CPU load average for the same period.
The load average consists of three values that represent 5, 10 and 15 minutes averages.

A load average that stays the same on a 'good performance' and on a 'performance degraded' one is an indication that you have to look elsewhere, perhaps at the network bandwidth, disk IO or the installed memory

Other commands that offer realtime view of the CPU per-process load is `ps -aux` and `top`. You may find a single process using more than 50% of the available CPU time. Using `nice` to decrease the execution priority of this process may boost performance.
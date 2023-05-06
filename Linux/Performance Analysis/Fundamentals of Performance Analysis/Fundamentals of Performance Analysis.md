# Fundamentals of Performance Analysis
## How to improve performance
The general guidelines for achieving a higher performance level on a typical [[Linux]] system:
- Make sure you have enough memory
- Use software/hardware load balancing systems. They not only provide faster responses from network apps but also provides redundancy.
- Review application specific documentation and configuration files. Some settings can boost app performance like turning on caching or running multiple instances
- Install faster disks to avoid storage IO bottenecks.
- Use RAID to distribute IO across disks. Not all apps benefit from striping and RAID and it can damage performance. Application/database vendors should be consulted before moving to RAID
- Monitor network bandwidth to ensure bandwidth is not saturated and error rate is minumum.

## Possible causes of bottlenecks
- Hardware wise it is either CPU, memory and disk/network IO
- Processes running on the system must have access to above components. They compete to have a CPU cycle or an IO from the disk to read and to read the data. If the component is busy it will have to wait for its turn. This wait time means that the system runs slower and implies that it is having performance issues
- A common misconception is that a faster CPU will eliminate all performance-related problems. The CPU is already the fastest component of the system. If the process is waiting for an IO to return with data, it will waste many CPU cycles waiting for the disk or network to respond. Also if the memory is full, the OS will start using the paging space on the disk to swap in and out memory pages. This slows things down as the disk is the slowest part of the system.

## [[Check your resources]]
## [[Memory Management]]
# CPUs, Cores and Hyperthreading
## Hyperthreading
Hyperthreading was Intel's attempt to bring parallel computation to conumser PCs. The first CPU was the Pentium 4 HT in 2002 which only had a single core meaning it could only really do one thing at a time, even if it could switch fast enough. Hyperthreading was designed to make up for this.

A single physical CPU core with hyperthreading appears as 2 logical CPUs to an OS. The CPU is still a single one and only has a single set of execution resources for each core. The CPU pretends to have more cores than it does and uses its own logic to speed up program execution. Hyperthreading allows the two logical CPUs to share physical execution resources which can speed things up. For example if one virtual CPU is stalled, the other can borrow its execution resources.

## Multiple Cores
Originally, CPUs only had a single core. To increase performance, manufacturers add additional cores, which appear as more CPUs to the OS. A CPU with two cores can run two processes at once which speeds up your system.

## Multiple CPUs
Most computers only have a single CPU. That single CPU can have multiple cores or hyperthreading but its still only a single CPU.

One thing that can be done is to add more CPUs (which was done before hyperthreading and multi-core CPUs) but this requires motherboard with multiple CPU sockets. This is not very common but can be found with supercomputers, servers and other high-end systems.
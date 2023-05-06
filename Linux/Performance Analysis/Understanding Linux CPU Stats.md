# Understanding Linux CPU stats
## The 3 CPU states
There are 3 general states a CPU can be in:
- **Idle**: has nothing to do
- **Running a user space program**: like a command shell, email server or compiler
- **Running the kernel**: servicing interrupts or managing resources

These 3 states can be further subdivided. For example, user space programs can be categorised as those running under their initial priority level or those running with a nice priority. Niceness is a way to tweak the priority level of a process so it can run less frequently. The niceness level ranges from -20 (most favourable) to 19 (least favourable). By default, processes on Linux are started with niceness of 0.

## The 7 CPU statistics explained
There are several different ways to see the various CPU statistics. Most common is probably using `top` command.

`%Cpu(s): 24.8 us,  0.5 sy,  0.0 ni, 73.6 id,  0.4 wa,  0.0 hi,  0.2 si,  0.0 st`

`24.8 us` means that the processor is spending 24.8% running user space processes

`73.6 id` means the processor was idle over 73% of the time

`0.5 sy` Amount of time CPU was spent running the kernel

`0.0 ni` How much time the CPU spent running processes that have been niced

`0.4 wa` Input and output operations

`0.0 hi` and `0.2 si` How much time has been spent servicing hardware and software interrupts

`0.0 st` For VMs. When Linux is running a virtual machine, st shows how long the virtual CPU has spent waiting for the hypervisor.

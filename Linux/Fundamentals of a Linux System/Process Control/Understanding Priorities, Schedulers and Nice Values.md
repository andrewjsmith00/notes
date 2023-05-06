# Understanding Priorities, Schedulers and Nice Values
If a process has a `PR` value of `rt` it is a realtime process which has its own scheduler compared to normal processes.

## CHRT
Allows you to manipulate real-time attributes of a process. There are 5 scheduling policies for processes. 2 are realtime, 3 are normal.

### SCHED_RR
Realtime. Sched round robin. If there are multiple realtime processes, each will get their fair share.

### SCHED_FIFO
Priority is higher than realtime processor. Up to process to release CPU.

### SCHED_OTHER
Default

### SCHED_IDLE
Runs only if there is an idle loop available. Low priority. Only run if system has nothing to do
### SCHED_BATCH
Optimised for batch processes

## Process Priority
Lower number priority goes before process with higher number.

## Nice values
Negative nice means less nice. Gets more attention from the CPU. Also subtracts from priority
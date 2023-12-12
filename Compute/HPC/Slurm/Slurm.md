Simple Linux Utility for Resource Management.

It is a [[Job Scheduler]] with optional plugins


You run [[slurmctld]] and would run a backup

There is a [[slurmdbd]] with a backup maybe. This can write to something like a [[MySQL]] database 

Compute nodes run [[slurmd]]
If you run multiple clusters you have a set of tools to manage them.
## Daemons
If you run with `-c` it will clear previous state
`-v` runs verbose messaging. Shows scheduling decisions, etc.

## Commands
- **sbatch** - Submits script for later execution (batch)
- **salloc** - Create job allocation and start shell
- **srun** - Create a job allocation and launch a job step
	- `—label` shows the node ID in output
	- `—-exclusive` provides exclusive access to the nodes
- **sattach** Connect stdin/out/err for an existing job or job step


When you run `srun` on [[Slurm]] it:
1. Sends a request to [[slurmctld]]
2. [[slurmctld]] grants allocation and returns details
3. `srun` sends step create request to [[slurmctld]]
4. [[slurmctld]] returns with step credential
5. `srun` opens communication sockets
6. `srun` forwards credential with task info to [[slurmd]]
7. [[slurmd]] forwards request as required
8. [[slurmd]] forks [[slurmstepd]]
9. [[slurmstepd]] connects to IO to run and launch tasks
10. When complete, [[slurmstepd]] talks to `srun`
11. `srun` notifies [[slurmctld]]
12. [[slurmctld]] confirms everything is cleaned up.
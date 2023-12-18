The default authentication and digital signature mechanism for [[Slurm]]

Each node needs a MUNGE key and be running the daemons.

The MUNGE credential includes:
- User ID
- Group ID
- Timestamp
- Whatever else may be needed to sign and/or encrypt
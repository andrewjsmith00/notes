# SLAs and Reporting in Airflow
## SLAs
The amount of time a task or a DAG should require to run.
An SLA miss is any time the task/DAG doesn't meet the expected timing.
If the SLA is missed, it sends an email and a log is stored. You can also see it under the SLA Misses link in the web UI.


## Defining SLAs
- Use the `sla` argument on the task with a `timedelta`
- Use the `default_args` dict on the DAG

## General Reporting
- Options for success/failure/error
- Handled via keys in default_args dictionary
- Can be sent with the EmailOperator
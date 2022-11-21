# Airflow Executors
## What is an executor?
Executor runs the tasks defined in DAGs. Different executors handle running tasks differently.

Example executor:
- [[SequentialExecutor]]
	- Runs a single task at a time.
	- The default executor
	- Useful for debugging
	- While functional, not recommended for production
- [[LocalExecutor]]
	- Runs on a single system
	- Treats each task as a process
	- *Parellelism* is defined by the user
	- Can utilise all resources of a system
- [[CeleryExecutor]]
	- Uses [[Celery]] backend as a task manager
	- Multiple worker systems can be defined
	- More difficult to setup & configure. Requires a working Celery installation and a way of sharing DAGs
	- Extremely powerful method for organisations with extensive workflows

## Determine your executor
You can look at the `airflow.cfg` file for the `executor=` line. Or you can run `airflow list_dags` where it will show the executor
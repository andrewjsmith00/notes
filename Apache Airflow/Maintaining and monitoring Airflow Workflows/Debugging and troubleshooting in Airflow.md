# Debugging and troubleshooting in Airflow
## Typical Issues
- DAG not running on schedule
	- Check if the scheduler is running (often visible in the web UI)
	- Run `airflow scheduler`
- DAG won't load into system
	- At least one `schedule_interval` hasn't passed
		- Modify the attributes to meet your requirements
	- Not enough tasks free within the executor to run
		- Change executor type
		- Add system resources'
		- Add more systems
		- Change scheduler
	- Verify the DAG is where its expected (check airflow.cfg for this)
	- Folder path Is absolute
- Syntax errors
	- Sometimes difficult to find errors in the DAG.
	- Most common reason a DAG file won't appear
	- Run `airflow list dags` where it will show the error
	- Run the file with Python. This won't give you an output normally but it can check for syntax errors
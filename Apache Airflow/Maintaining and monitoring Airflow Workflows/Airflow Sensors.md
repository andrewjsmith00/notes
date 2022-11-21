# Airflow Sensors
## What is a sensor?
An operator that waits for a certain condition to be true such as:
- Creation of a file
- Upload of a database record
- Certain response from a web request

You can define how often to check for the condition to be true and are assigned to tasks.

## Sensor details
All sensors are defined from `airflow.sensors.base_sensor_operator`

Sensor arguments:
- `mode`: How to check for the condition
	- `poke`: Default. Run repeatedly
	- `reschedule`: Give up task slot and try again later
- `poke_interval`: How often to wait between checks
- `timeout`: How long to wait before failing tasks


## File sensor
- Checks for the existence of a file ata certain location or if any files exist in a directory

## Other sensors
`ExtenalTaskSensor` - wait for a task in another DAG to complete
`HttpSensor` - Wait for web request

## Why sensors?
- You're uncertain when a condition is true?
- If failure not immediately desired
- Add task repetition without loops
# Airflow Scheduling
## DAG Runs
DAG Runs are an instance of a workflow at a given point in time.

You can run a DAG manuually or via `schedule_interval`

You can maintain state for each workflow and the tasks within via the states:
- `running`
- `failed`
- `success`

## Schedule details
When scheduling a DAG, there are several attributes of note:
- `start_date` - The date/time to initally schedule the DAG run
- `end_date` - Optional attribute for when to stop running new DAG instances
- `max_tries` - Optional attribute for how many attempts to make
- `schedule_interval` - How often to run

### Schedule Interval
How often to schedule DAG runs between `start_date` and `end_date`. This is a minimum/maximum value.

This can be done via `cron` style format or via Airflow scheduler presets.
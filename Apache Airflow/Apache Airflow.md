# Apache Airflow
## What is a workflow?
A set of steps to accomplush a given data engineering task. This can be of varying levels of complexity.

## What is Airflow?
Airflow is a platform to program workflows including:
- Creation
- Scheduling
- Monitoring

Airflow can use many tools and languages but the workflow is writtin in [[Python]]. These workflows are implemented via DAGs.

These DAGs consist of the tasks and their dependencies between tasks.

It can be accessed by code, CLI or a web server.

## Running a workflow in Airflow
Running a simple Airflow task.

```shell
airflow run <dag_id> <task_id> <start_date>
```

Using a DAG named *example-etl*, a task named *download-file* and a start date of 2020-01-10

```shell
airflow run example-etl download-file 2020-01-10
```


## [[Introduction to Apache Airflow]]

## [[Implementing Airflow DAGs]]

## [[Production Pipelines in Airflow]]
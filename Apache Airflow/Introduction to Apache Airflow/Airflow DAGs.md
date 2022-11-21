# Airflow DAGs
## What is a DAG?
A DAG ([[Directed Acylic Graph]]) is:
- Directed. There is a flow representing dependencies between components
- Acylic, does not loop/cycle/repeat
- Graph, the set of components

DAGs appear in many places including [[Apache Airflow]], [[Luigi]] and [[Apache Spark]]

## DAG in Airflow
In Airflow DAGS are:
- Written in [[Python]] but can use components in other languages
- Made ip of components (tasks) to be executed such as operators, sensors, etc.
- Contain dependencies explicitly or implicitly
	- Ie. Downloading a file before loading it into a database

## Define a DAG
Example DAG:
```Python
from airflow.models import DAG
from datetime import datetime
# Default arguments
default_arguments = {
	"owner": "andjsmi",
	"email": "andjsmi@amazon.com",
	"start_date": datetime(2020,1,20) # Earliest time a DAG can be run
}

# Define DAG. First argument is the name
etl_dag = DAG('etl_workflow', default_args=default_arguments)
```

## DAGs on the command line:
Using `airflow`:
- the `airflow` CLI contains many subcommands
- `airflow -h` for desciriptions. Many are related to DAGs
- `airflow list_dags` to show all recognised DAGs

## Command line vs Python
### Command line
- Start Airflow processes
- Manually run DAGs/Tasks
- Get logging information from Airflow

### Python
- Create DAG
- Edit properties of DAG
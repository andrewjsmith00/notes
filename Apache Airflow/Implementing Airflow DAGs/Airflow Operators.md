# Airflow Operators
[[Apache Airflow]] operators are a single task in a workflow. These typically run independently and do not are information between each other. It is possible however.

Airflow has many operators used to perform different tasks.


## Operator Gotchas
Operators are not guaranteed to run in the same location/environment.
They may require extensive use of environment variables
It can be difficult to run tasks with elevated privileges

## BashOperator
The [[Bash]] operator will execute a given Bash command or script. This is run in a temporary directory.

You can specify environment variables for the command.

An example below:

```python
from airflow.operators.bash_operator import BashOperator

example_task = BashOperator(task_id='bash_ex',
						   bash_command='echo 1',
						   dag=dag)
```



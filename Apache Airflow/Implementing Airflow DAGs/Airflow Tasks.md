# Airflow Tasks
Tasks are instances of operators. These are usually assigned to a variable in Python.

In Airflow, these are referred to by the task ID.

## Task Dependencies
These define a given order to task completion. These are not required for a workflow but present in most. These are referred to as *upstream* or *downstream* tasks. 

Since Airflow 1.8, dependencies are defined using the *bitshift* operators
`>>` upstream
`<<` downstream

## Upstream vs Downstream
*Upstream* means before
*Downstream* means after

## Simple Task Dependency
Define the tasks
```python
task1 = BashOperator(task_id='task_1',
					bash_command='echo 1',
					dag=dag)

task2 = BashOperator(task_id='task_2',
					bash_command='echo 2',
					dag=dag)

# Set task_1 to run before task_2
task1 >> task2 # or task2 << task1
```


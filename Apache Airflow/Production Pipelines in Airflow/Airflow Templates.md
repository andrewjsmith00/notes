## What are templates
Templates allow for substitution of information during a [[Airflow DAGs]] run. They provide added flexibility when defining tasks and are created using the [[Jinja]] templating language.


## Templated BashOperator example
```python
templated_command = "Reading {{ params.filename}}"

T1 = BashOperator(task_id='template_task',
				 Bash_command=templated_command,
				 Params={"filename": "file1.txt"}
				 DAG=example_dag)

```

Output:
```
Reading file1.txt
```

Continuing:

```python
templated_command = "Reading {{ params.filename}}"

T1 = BashOperator(task_id='template_task',
				 Bash_command=templated_command,
				 Params={"filename": "file1.txt"}
				 DAG=example_dag)
T2 = BashOperator(task_id='template_task',
				 Bash_command=templated_command,
				 Params={"filename": "file2.txt"}
				 DAG=example_dag)
```



## More advanced template
[[Jinja]] templates are quite powerful and allow for for loops, etc.

Ie.
```Python
Templated_command = """
{% for filename in params.filename %}
	Echo "Reading {{ filename }}"
{% endfor %}
"""

T1 = BashOperator(task_id='Template_task',
			bash_command=templated_command,
			params={'filenames: ['file1.txt','file2.txt']}
			dag = example_dag)
```

## [[Airflow Variables]]
As part of the templating system, Airflow provides a series of built-in runtime variables. These provide information about DAG runs, tasks and system configuration.

This includes things like:
Execution date as `ds` and `dn_nodash` as well as previous execution dates, DAG object and the Airflow configuration object.

Refer to https://airflow.Apache.org/docs/stable/macros-ref.html for more



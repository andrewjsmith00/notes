Branching in [[Apache Airflow]]
- provides conditional logic
- One example is through the `BranchPythonOperator`
- This function takes the parameters and then returns the task ID to run.

```python
def branch_test(**kwargs):
	if int(kwargs['ds_nodash']) % 2 == 0:
		return 'even_day_task'
	else:
		return 'odd_day_task'

branch_task = BranchPythonOperator(task_id='branch_task', dag=dag,
								   provide_context=True,
								   python_callable=branch_test)
```
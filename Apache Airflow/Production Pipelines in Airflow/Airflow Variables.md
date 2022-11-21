As part of the templating system, [[Apache Airflow]] provides a series of built-in runtime variables. These provide information about DAG runs, tasks and system configuration.

This includes things like:
Execution date as `ds` and `dn_nodash` as well as previous execution dates, DAG object and the Airflow configuration object.

Refer to https://airflow.Apache.org/docs/stable/macros-ref.html for more

## Macros
In addition to others, there is also a `{{ macros }}` variable. This is a reference to the Airflow macros package which provides various useful objects / methods for [[Airflow Templates]].

This lets you get [[Python]] datetime and timedelta, Python's uuid and more.
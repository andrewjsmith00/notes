# [[Glue]] ETL Engine
The ETL engine performs [[ETL]] on the datasets discovered and registered in the [[Glue Data Catalog]]. The ETL Engine will generate [[Python]] [[PySpark]] code based on supplied configuration of source and destination. Alternatively you can write your own scripts.

## Job Scheduler
The job scheduler will trigger and monitor your jobs for the ETL engine. You can configure a trigger to run based on a schedule or completion of another [[ETL]] job or on demand.


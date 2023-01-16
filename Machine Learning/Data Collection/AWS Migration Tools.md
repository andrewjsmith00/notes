# AWS Migration Tools
## [[Data Pipeline]]
Allows you to process and move data between services and on-premises. This lets you choose a source and then move it to [[S3]].

You can also use Data Pipeline as a transformation tool.

## [[DMS]]
This lets you migrate data from one database to another. You can also put the output on to S3. DMS doesn't really support transformations, but it isn't really made for that.

## [[Glue]]
[[Glue]] is a managed [[ETL]] service. When you use [[Glue]], it creates tables in a [[Glue Data Catalog]] with the metadata and other information.
To create these tables you set up a [[Glue Crawler]] that looks at the data and infers the schema. If the crawler can't figure it out, it invokes the next one to try and recognise the data. You can also create custom classifiers.

With [[Glue]], you can take data from one source and output the data into other services.
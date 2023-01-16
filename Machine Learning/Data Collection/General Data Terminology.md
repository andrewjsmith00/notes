# General Data Terminology
Data is integral to ML. Understanding the terminology allows us to define and describe our data.

## Datasets
Collection of data for input. The data we use in ML

Columns are the attributes/features of the data. The categories.
Rows are the observations of the data.

### Structured data
Data with a defined schema (information about the data) such as attribute names and assigned data types

### Unstructured data
No defined schema or structure. Majority of data collected

### Semi-structured
Too unstructured for relational data but has some structure such as CSV, XML, other [[NoSQL]] formats.

## [[Data Warehouse]]s
Data warehouses collect data from many sources in many formats. There will typically be some sort of processing/cleaning beforehand in order to use analytics and BI tools on the data.

## [[Data Lakes]]
These store mass amounts of unstructured data in a single place. Store historical data or data we don't know what to do with yet. No preprocessing done to the data. Processing is done on export and the raw data may not be ready for use.
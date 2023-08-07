# [[S3]] Storage Classes
## S3 Standard
- Highly available and durable. Data is stored redundantly across multiple devices in multiple facilities
- Designed for frequent access
- Suitable for most workloads. Is the default class. Useful for websites, content distribution etc.

## S3 Standard-Infrequent Access
- Used for data that is accessed less frequently
- You pay to access the data
- Use cases: long-term storage, backups and as a data store for disaster recovery files.

## S3 One Zone-Infrequent Access
- Data is stored redundantly in a single AZ
- 20% cheaper than Standard-IA
- Great for long-lived, infrequently accessed, non-critical data

## [[Glacier]]
- Long-term data archiving with retrieval times of 1 minute to 12 hours. Pay to access. Useful for data only accessed a few times per year

## Glacier Deep Archive
- Archiving rarely accessed data with a default retrieval time of 12 hours

## Intelligent Tiering
- Automatically moves your data to the most cost-effective tier based on how often the data is accessed
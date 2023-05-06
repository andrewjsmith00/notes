# Securing your bucket with [[S3]] Block Public Access
## Object ACLs vs Bucket Policies
Object ACLs work on an individual object level. You can provide a specific file ceratin permissions for usage etc.

If you want to make everything public you can use a bucket policy to do so.

## Notes
- Buckets are private by default
- When you upload a file to [[S3]] successfully you receive a HTTP 200 status code in response
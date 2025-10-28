Interview Questions

1)Someone accidently deleted data from s3, how can we recover it?
s3 versioning needs to be enabled
In case versioning was disabled ,would restore data from backups, cross-region replicas, or AWS Backup vaults
I’d enable bucket versioning, object lock, lifecycle policies, MFA delete, and least-privilege IAM policies.
In production, we never rely on a single protection mechanism. Versioning + Object Lock + Backup is the recommended layered approach

2) How do you identify who deleted the object?
Check AWS CloudTrail logs (DeleteObject event)
View User ARN/IP/API call time
Use CloudWatch alerts

3)What are s3 Lifecycle rules?
S3 Lifecycle Rules are policies that you configure on an S3 bucket to automate the transition and expiration of objects based on their age, storage class, or versioning state. They help optimize storage cost, performance, and data retention automatically.
We can transition data from S3 Standard to IA after 30 days, then to Glacier after 90 days, and optionally delete after a retention period. 
Lifecycle rules also handle version cleanup, delete markers, and incomplete multipart uploads. 
They help in automating cost optimization and housekeeping of S3 buckets.”




---
title: "Week 7 Worklog"
date: 2026-07-13
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---
### Week 7 Objectives:

* Understand and integrate AWS S3 for file/image storage.
* Understand and integrate an AWS managed database service (RDS/DynamoDB) for the application.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | - Learn about S3 concepts<br>&emsp; + Bucket<br>&emsp; + Object<br>&emsp; + Permissions<br>- Create S3 bucket, configure bucket policy & CORS | 13/07/2026 | 13/07/2026 | https://docs.aws.amazon.com/s3/ |
| 3 | - Integrate AWS SDK into backend for upload/download files<br>- Implement file upload feature (images, documents) using S3 | 14/07/2026 | 14/07/2026 |  |
| 4 | - Research RDS and DynamoDB, compare with self-hosted database<br>- Create RDS instance / DynamoDB table, configure security | 15/07/2026 | 15/07/2026 | https://docs.aws.amazon.com/rds/ |
| 5 | - Migrate schema/data to the managed database<br>- Update backend application to connect to the new database service | 16/07/2026 | 16/07/2026 |  |
| 6 | - Test file upload/download and database connectivity<br>- Optimize file access (presigned URL) and monitor database performance | 17/07/2026 | 17/07/2026 |  |

### Week 7 Achievements:

* Understood S3 core concepts and created a properly configured S3 bucket.
* Implemented file upload/download features using the AWS SDK and S3.
* Understood the differences between RDS and DynamoDB and when to use each.
* Created and secured a managed database instance/table, and migrated data to it.
* Updated the backend application to work with S3 and the new managed database, verified with tests.

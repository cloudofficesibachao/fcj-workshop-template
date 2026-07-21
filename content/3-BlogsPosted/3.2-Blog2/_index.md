---
title: "Blog 2"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.2. </b> "
---

Building a Modern, Reliable, Multi-Region Data Architecture with AWS Glue and AWS Lake Formation
1. Objectives
To build a Multi-Region Data Lake on AWS to:
Ensure high availability.
Support disaster recovery (DR).
Manage and share data centrally.
Provide granular access control down to the table, column, or row level.
Support real-time and batch data analysis.

2. Overall Architecture
+----------------+
| Data Sources |

| ERP, CRM, IoT |

+-------+--------+
|
AWS Glue Jobs

|
▼
Amazon S3 Data Lake (Primary Region)
|

+--------------+--------------+
| |
AWS Glue Data Catalog Lake Formation
| |

+--------------+--------------+
|
Amazon Athena
|
Amazon QuickSight
|
Business Users
Cross-Region Replication
│
▼
Amazon S3 (Secondary Region)

|
Glue Catalog Replication
|
Lake Formation
|
Athena / EMR / Redshift
3. New Features of the Services
AWS Glue
Glue Data Quality
Automatic data quality checking.
Detects missing values.
Detects anomalous data.
Generates Data Quality reports.

Glue Flex Jobs
Lower cost for ETL tasks that don't require immediate processing.
Suitable for scheduled or non-urgent jobs.

Glue Studio
Intuitive ETL design (drag-and-drop).
Automatic PySpark code generation.
Easier to maintain and reduced development time.

Glue 5.0
Supports the latest Spark version.
Improved processing performance.
Supports the new Python.

Optimized for Apache Iceberg, Hudi, and Delta Lake.

AWS Lake Formation
LF-Tags
Manage permissions based on tags instead of individual tables.
Example:
Department = Finance
Sensitivity = Confidential
All tables with the same tag will inherit the access policy.

Row-Level Security
Example:
User A
View-only
Region = Hanoi

Column-Level Security
Example:
Salary
View-only HR
Cross-Account Sharing
Share Data Lake between multiple AWS accounts without copying data.

Hybrid Access Mode
Combines permission management with IAM and Lake Formation to support migrations or existing systems.

4. Benefits of the Architecture
Criteria
Solution
High Availability
Data is copied to a redundant Region using S3 Cross-Region Replication. Disaster Recovery
Avoid switching to a second region when the primary region fails.
Data Governance
Lake Formation manages access centrally and granularly.
Scaleability
Glue, Athena, and S3 are all serverless services that automatically scale as needed.
Security
Data encryption with AWS KMS, authorization using IAM and Lake Formation, and logging with CloudTrail.
Performance
Parquet, Partition, Compression, and Athena Engine v3 help reduce query times.
Cost Optimization
Utilizing Glue Flex Jobs, S3 Lifecycle, Query Result Reuse, and column formatting (Parquet) reduces storage and analytics costs.
Conclusion
The architecture using AWS Glue and AWS Lake Formation helps build a modern, multi-regional, and reliable data lake with centralized data governance, granular authorization, and good integration with analytics services like Athena and QuickSight. Combined with Amazon S3 Cross-Region Replication, Glue Data Quality, Glue Flex Jobs, LF-Tags, Apache Iceberg, and storage optimization techniques such as Parquet, Partition, and Lifecycle Policies, this will provide a highly scalable data platform that meets the availability, security, and cost-effectiveness requirements of businesses.

(Source: https://awsstudygroup.com/2023/05/06/xay-dung-kien-truc-du-lieu-hien-dai-da-region-va-dang-tin-cay-bang-cach-su-dung-aws-glue-va-aws-lake-formation/)<img width="807" height="342" alt="Screenshot 2026-07-21 003953" src="https://github.com/user-attachments/assets/6430e2a6-b4bf-4661-b430-54000888398b" />
<img width="849" height="405" alt="Screenshot 2026-07-21 003923" src="https://github.com/user-attachments/assets/c564ae13-4379-43ea-b7d8-85ae146c0ce4" />
<img width="560" height="591" alt="Screenshot 2026-07-21 003857" src="https://github.com/user-attachments/assets/15c3686c-7997-4e5a-a9ab-9d01d6e67e37" />

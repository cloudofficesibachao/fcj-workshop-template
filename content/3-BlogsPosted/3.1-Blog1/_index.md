---
title: "Blog 1"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

How to Use AD FS Users and Tableau to Securely Query Data in AWS Lake Formation Objective: To build a solution that allows enterprise users to log in with Active Directory (AD FS) accounts, access Tableau, and only view data they have permissions to access in AWS Lake Formation. Architecture: User │ ▼ Active Directory │ AD FS (SAML) │ ▼ AWS IAM Identity Center / IAM Role │ ▼ Tableau Server / Tableau Cloud │ Athena │ Lake Formation │ Amazon S3 Data Lake Security Benefits: Single Sign-On (SSO) login with an AD account. No need to create separate IAM users. Complies with enterprise password policies.

No Access Key required. Tableau does not need to store Access Keys or Secret Keys. AWS provides temporary credentials after successful authentication.

Fine-grained Access Control Lake Formation supports: Row-level Security, Column-level Security, Cell Filtering. For example: Accountants can see the Salary column. Employees can only see the Employee Name. Managers can only see data for their department. Audit: All queries are logged via: AWS CloudTrail Athena Query History, Lake Formation Audit Logs. This helps track who accessed the data, when, and what queries were made. New features of AWS services: Some notable features that can be applied: AWS Lake Formation Fine-grained access control. Row-level and column-level security. LF-Tags for managing permissions by label. Sharing data between multiple AWS accounts using AWS RAM. Integration with IAM Identity Center. Amazon Athena Athena Engine v3 with improved performance. Prepared Statements. Query Result Reuse. Apache Iceberg supports ACID. Query data directly on S3. Amazon S3 S3 Intelligent-Tiering. S3 Access Points. S3 Object Lambda. S3 Versioning. Lifecycle Rules automatically migrate data to a low-cost storage layer. Tableau supports SAML SSO. Direct connection to Athena. Live Connection. Extract Refresh. Integrated Row-Level Security.

IAM Identity Center: Centralized user and group management. Federation with AD FS. Temporary Credentials. Permission Sets. Cost Optimization: - Data storage in Parquet format. Instead of CSV, use Parquet. Benefits: Reduced storage space. Athena only reads necessary columns. Significantly reduces query costs. - Data Partitioning: Example: /year=2025 /month=07 /day=15. Athena only scans relevant partitions instead of the entire data.

- Data Compression: Use Snappy ZSTD GZIP to reduce data scanning size and costs. - Lifecycle Policy: Set rules: New data → S3 Standard. After 30 days → S3 Standard-IA. After 90 days → Glacier Instant Retrieval. After 1 year → Glacier Deep Archive. -Query Result Reuse: Athena can reuse query results if the data doesn't change, reducing the number of data scans and costs.

CloudFront (if there is a public dashboard): If Tableau is embedded in a web portal and has static content, CloudFront can be used to speed up delivery and reduce server load.
Auto Scaling: If Tableau Server runs on: Amazon EC2. Amazon ECS can be configured for Auto Scaling to scale up when many users access and shrink when load is low, optimizing operating costs. (Reference link: https://awsstudygroup.com/2022/08/16/cach-su-dung-ad-fs-user-va-tableau-de-truy-van-du-lieu-mot-cach-an-toan-trong-aws-lake-formation/)<img width="789" height="580" alt="Screenshot 2026-07-21 001955" src="https://github.com/user-attachments/assets/a89c29a8-33c1-43e2-9b7d-2b942c18feda" />

---
Title: "CloudOffice Project Proposal"
Date: 2026-07-20
Weight: 2
Chapter: False
Previous: " 2. </b> "
---






# CloudOffice – AWS Office Rental Management System

# IoT Weather Platform for Lab Research
## Unified AWS Serverless Solution for Real-Time Weather Monitoring

### 1. Operational Summary
The IoT Weather Platform was designed for the *ITea Lab* team in Ho Chi Minh City to enhance weather data collection and analysis capabilities. The platform supports up to 5 weather stations, scalable to 10–15 stations, using Raspberry Pi edge devices combined with ESP32 sensors to transmit data via MQTT. The platform leverages AWS Serverless services to provide real-time monitoring, predictive analysis, and cost savings, with limited access for 5 lab members via Amazon Cognito.

### 2. Problem Statement
*Current Problem* Current weather stations require manual data collection, making management difficult with multiple stations. There is no centralized system for real-time data or analytics, and third-party platforms are often expensive and overly complex.

*Solution*
The platform uses AWS IoT Core for MQTT data reception, AWS Lambda and API Gateway for processing, Amazon S3 for storage (including the data lake), and AWS Glue Crawlers and ETL tasks to extract, transform, and load data from the S3 data lake to another S3 bucket for analysis. AWS Amplify with Next.js provides the web interface, and Amazon Cognito ensures secure access. Similar to Thingsboard and CoreIoT, users can register new devices and manage connections, but this platform operates on a smaller scale and serves internal purposes. Key features include real-time dashboards, trend analysis, and low operating costs.

*Benefits and Return on Investment (ROI)*
The solution provides a fundamental platform for lab members to develop a larger IoT platform, while also providing data for AI researchers to train models or perform analysis. The platform reduces manual reporting for each station through a centralized system, simplifies management and maintenance, and improves data reliability. Estimated monthly cost is $0.66 (according to AWS Pricing Calculator), totaling $7.92 for 12 months. All IoT devices are already equipped from the existing weather station system, with no additional development costs. The payback period is 6–12 months due to significant savings in manual operation time.

### 3. Solution Architecture
The platform uses an AWS Serverless architecture to manage data from 5 Raspberry Pi-based stations, scalable to 15 stations. Data is received via AWS IoT Core, stored in an S3 data lake, and processed by AWS Glue Crawlers and ETL jobs to transform and load into another S3 bucket for analysis. Lambda and API Gateway handle additional processing, while Amplify with Next.js provides a console secured by Cognito.

![IoT Weather Station Architecture](/images/2-Proposal/edge_architecture.jpeg)

![IoT Weather Platform Architecture](/images/2-Proposal/platform_architecture.jpeg)

*AWS Services Used*
- *AWS IoT Core*: Receives MQTT data from 5 stations, expandable to 15.
- *AWS Lambda*: Processes data and triggers Glue jobs (2 functions).
- *Amazon API Gateway*: Communicates with the web application. - *Amazon S3*: Stores raw data (data lake) and processed data (2 buckets).

- *AWS Glue*: Crawlers index the data, ETL jobs transform and load the data.

- *AWS Amplify*: Stores the Next.js web interface.

- *Amazon Cognito*: Manages access rights for lab users.

*Component Design*

- *Edge Device*: Raspberry Pi collects and filters sensor data, sending it to IoT Core.

- *Data Reception*: AWS IoT Core receives MQTT messages from the edge device.

- *Data Storage*: Raw data is stored in the S3 data lake; processed data is stored in another S3 bucket.

- *Data Processing*: AWS Glue Crawlers index the data; ETL jobs transform it for analysis. - *Web Interface*: AWS Amplify hosts the Next.js application for dashboards and real-time analytics.

- *User Management*: Amazon Cognito limits active accounts to 5.

### 4. Technical Implementation
*Implementation Phases*
The project consists of two parts — setting up a boundary weather station and building a weather platform — each part goes through 4 phases:

1. *Research and Architectural Design*: Researching Raspberry Pi with ESP32 sensors and designing the AWS Serverless architecture (1 month before the internship).

2. *Cost Calculation and Feasibility Testing*: Using AWS Pricing Calculator to estimate and adjust (January).

3. *Architectural Adjustments for Cost/Solution Optimization*: Refinements (e.g., optimizing Lambda with Next.js) to ensure efficiency (February). 4. *Development, Testing, Deployment*: Programming Raspberry Pi, AWS services with CDK/SDK and Next.js application, then testing and putting it into operation (February–March).

*Technical Requirements*
- *Border Weather Station*: Sensors (temperature, humidity, precipitation, wind speed), ESP32 microcontroller, Raspberry Pi as the main component.

<img width="987" height="552" alt="z8017702787875_29f6937410b357be65366c9febe426db" src="https://github.com/user-attachments/assets/459320d0-36b1-49f8-ab46-c6dda4de685d" />

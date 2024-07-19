# Realtime Data Streaming 
## Introduction 
This project serves as a comprehensive guide to building an end-to-end data engineering pipeline. It covers each stage from data ingestion to processing and finally to storage, utilizing a robust tech stack that includes Pyspark, S3, Glue crawler, Glue ETL, EventBridge, Redshift, SNS, Step Functions, and SQL. Everything is set using AWS services.


## System Architecture
![System Architecture](Airline_Data_Ingestion_Project/architecture.png)

The Project is designed with the following components:
- **Data Source**: we use Airline Dataset in CSV format, there are two files Dimension table and fact table.
- **S3**: Where the file will land.
- **Event Bridge**: For detecting the file landed on the source destination.
- **Glue Crawler**: For crawling out the file from the S3 path and feeding it Glue ETL.
- ** Glue ETL**: For the  Extract Transform Load on the Data Set and Join Operations on the two data tables.
- **SNS**: Simple Notification System for the processing success or failure
- **Redshift**: Warehouse to store the data after the processing
- **Step Function**: For Orchestration of the whole process and additional implementation.
- ** Cloud Trail**: For user logs and other inputs and outputs.

## Learnings 

-Setting up a data pipeline using AWS services.
-Real-time data ingestion using Glue and GLue ETL processes.
-Notification for alerting.
-Database Warehousing for storing the processed data.
-Automating the whole task as soon as a file lands on the source destination.

## Technologies

- AWS
- S3
- S3 Cloud Trail Notification
- Event Bridge Pattern Rule.
- Glue Crawler
- Glue ETL
- SNS for notification
- Redshift
- Step Function

## Executions
- Step:1: The File First Lands on the S3 source data location.
- Step 2: Glue crawlers are created for crawling out the file from the source to glue ETL jobs
- Step 3: Glue ETL job is then performed on the data, and the two tables dimension table and fact table are joined and processed.
- Step 4: Event Bridge Rule is then implemented for detecting when and file lands on s3 and forwards it to the glue crawler.
- Step 5: After that, we create Schema on the Redshift database for both the files, to ingest the data.
- Step 6: Step Function is then implemented for orchestrating the whole process and additional parameters then data is ingested onto the redshift.
-Step 7: Finally the S3 cloud Trail is implemented for the final touches.























# Cloud-Based Event-Driven Data Pipeline on AWS

## Overview
This project demonstrates the design and implementation of an event-driven data pipeline on AWS that ingests raw event data, validates it, applies transformations, and produces analytics-ready datasets.

## Problem Statement
Organizations receive large volumes of incoming event data (documents, transactions, logs) that must be validated, transformed, and made analytics-ready in a reliable and scalable way. Manual processing leads to delays, data quality issues, and poor observability.

## Architecture
Raw Events (JSON/CSV)
        ↓
   S3 (raw bucket)
        ↓ (event trigger)
   AWS Lambda (validation)
        ↓
 AWS Step Functions (orchestration)
        ↓
   Transform Lambda / Glue Job
        ↓
   S3 (curated bucket - Parquet)
        ↓
   Athena / SQL-ready

## Data Flow
1. Raw event files are uploaded to an S3 raw bucket
2. S3 event triggers a Lambda function for validation
3. Step Functions orchestrates the pipeline with retries and error handling
4. Data is transformed and written to a curated S3 bucket in Parquet format
5. Curated data can be queried using Athena

## Technologies Used
- AWS S3
- AWS Lambda
- AWS Step Functions
- AWS Glue (optional)
- Python
- SQL
- CloudWatch

## Key Features
- Event-driven ingestion
- Data validation and schema checks
- Retry and failure handling
- Monitoring and logging
- Analytics-ready output

## What I Learned
- Designing reliable cloud data pipelines
- Handling failures in distributed systems
- Applying data engineering best practices on AWS

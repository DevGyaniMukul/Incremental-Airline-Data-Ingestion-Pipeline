# Incremental Airline Data Ingestion Pipeline

An event-driven data engineering pipeline for incrementally ingesting, processing, cataloging, and loading airline datasets into Amazon Redshift using Amazon S3, AWS Glue, Glue Crawlers, EventBridge, and Step Functions.

---

## 📋 Project Overview

This project demonstrates an **event-driven ETL pipeline** for processing airline datasets.

Raw airline data is stored in **Amazon S3**, where AWS Glue is used for ETL processing and schema discovery. **Glue Crawlers and the AWS Glue Data Catalog** provide automated metadata and schema management.

The pipeline uses **Amazon EventBridge and AWS Step Functions** to orchestrate ingestion workflows and ultimately loads curated data into **Amazon Redshift** for analytical workloads.

---

## 🏗️ Architecture

```text
┌──────────────────┐
│   Airline Data   │
│   Source Files   │
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│    Amazon S3     │
│   Raw Data Zone  │
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│   AWS Glue       │
│ ETL Processing   │
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│  Glue Crawler    │
│ Schema Discovery │
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│ Glue Data Catalog│
│ Metadata Layer   │
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│   EventBridge    │
│ Event Triggering │
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│ Step Functions   │
│  Orchestration   │
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│ Amazon Redshift  │
│ Data Warehouse   │
└──────────────────┘
🎯 Key Features
- 🔄 Incremental Ingestion: Processes newly available airline datasets.
- ☁️ Amazon S3 Storage: Uses S3 as the cloud storage layer for airline data.
- 🛠️ AWS Glue ETL: Processes and transforms incoming datasets.
- 🔍 Automated Schema Discovery: Uses Glue Crawlers to discover dataset schemas.
- 📚 Metadata Management: Maintains metadata using the AWS Glue Data Catalog.
- ⚡ Event-Driven Processing: Uses Amazon EventBridge to initiate workflows.
- 🎛️ Workflow Orchestration: Uses AWS Step Functions to coordinate ingestion.
- 🏢 Data Warehouse Loading: Loads curated airline data into Amazon Redshift.

Incremental-Airline-Data-Ingestion-Pipeline/

├── glue/
│   └── airline_etl_job.py             # AWS Glue ETL job
│
├── step_functions/
│   └── ingestion_workflow.json        # Workflow definition
│
├── data/
│   └── airline_data/                  # Sample airline datasets
│
├── sql/
│   └── redshift_queries.sql            # Analytical queries
│
└── README.md                          # Project documentation

🔧 Technical Components
1. Amazon S3
Amazon S3 acts as the storage layer for airline datasets.
Incoming airline files are stored in S3 before being processed by the ETL pipeline.
2. AWS Glue ETL
AWS Glue performs the data processing and transformation required before the data is loaded into the warehouse.
The ETL layer is responsible for:
- Reading airline datasets
- Processing incoming data
- Applying transformations
- Preparing curated datasets
- Loading data into the downstream warehouse
3. Glue Crawlers
Glue Crawlers automatically discover the schema of the datasets stored in Amazon S3.
This reduces the need for manually defining schemas for incoming datasets.
4. AWS Glue Data Catalog
The Glue Data Catalog provides a centralized metadata layer.
It maintains information about:
- Dataset schemas
- Tables
- Data locations
- Metadata required by downstream processing
5. Amazon EventBridge
EventBridge provides the event-driven trigger mechanism for the pipeline.
It allows ingestion workflows to be initiated when relevant events occur.
6. AWS Step Functions
Step Functions orchestrates the different stages of the ingestion workflow.
Event
  ↓
EventBridge
  ↓
Step Functions
  ↓
Glue Processing
  ↓
Curated Data
  ↓
Redshift

7. Amazon Redshift
Amazon Redshift acts as the analytical data warehouse.
Curated airline datasets are loaded into Redshift for downstream analytics and reporting.

🔄 Data Processing Flow
New Airline Dataset
        ↓
Amazon S3
        ↓
EventBridge
        ↓
Step Functions
        ↓
AWS Glue ETL
        ↓
Data Transformation
        ↓
Glue Data Catalog
        ↓
Curated Dataset
        ↓
Amazon Redshift

☁️ AWS Services Used
Service	Purpose
Amazon S3	Raw and curated data storage
AWS Glue	ETL processing
Glue Crawler	Schema discovery
Glue Data Catalog	Metadata management
Amazon EventBridge	Event-driven triggering
AWS Step Functions	Workflow orchestration
Amazon Redshift	Data warehouse
🎯 Learning Objectives
This project demonstrates:
1. Incremental Data Ingestion
2. Event-Driven Architecture
3. AWS Glue ETL
4. Schema Discovery
5. Metadata Management
6. Workflow Orchestration
7. Cloud Data Warehousing
8. Amazon Redshift
9. AWS Data Engineering
10. Automated Data Pipelines
💼 Business Value
- Automates airline data ingestion.
- Reduces manual ETL intervention.
- Supports incremental processing.
- Provides centralized metadata management.
- Enables event-driven pipeline execution.
- Makes curated airline data available for analytics.
- Provides a scalable cloud data warehouse architecture.
🛠️ Built With
Amazon S3 · AWS Glue · Glue Crawlers · Glue Data Catalog · Amazon EventBridge · AWS Step Functions · Amazon Redshift

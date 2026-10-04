# AdTech Streaming Data Processing Pipeline

A real-time data engineering pipeline for processing, enriching, transforming, and querying advertisement events using Amazon Kinesis, Apache Flink, AWS Glue, Apache Iceberg, Amazon S3, and Amazon Athena.

---

## 📋 Project Overview

This project demonstrates a **real-time streaming data processing pipeline** designed to process advertisement events as they are generated.

The pipeline uses **Amazon Kinesis** for real-time event ingestion and **Apache Flink** for stream processing and enrichment. Processed data is transformed through **AWS Glue ETL jobs** and stored in **Apache Iceberg tables on Amazon S3**.

The resulting curated dataset is registered through the **AWS Glue Data Catalog** and made available for analytical querying using **Amazon Athena**.

---

## 🏗️ Architecture

```text
┌──────────────────┐
│ Advertisement   │
│     Events       │
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│   Amazon Kinesis │
│  Stream Ingestion│
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│   Apache Flink   │
│ Stream Processing│
│   & Enrichment   │
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│    AWS Glue      │
│ ETL / Validation │
│ & Transformation │
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│ Apache Iceberg   │
│  on Amazon S3    │
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│ AWS Glue Data    │
│     Catalog      │
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│  Amazon Athena   │
│ Analytical Query │
└──────────────────┘
🎯Key Features
- ⚡ Real-Time Processing: Processes advertisement events using Amazon Kinesis and Apache Flink.
- 🔄 Stream Enrichment: Enriches incoming advertisement events during stream processing.
- 🛠️ ETL Processing: Uses AWS Glue for validation and transformation.
- 🗂️ Lakehouse Storage: Stores curated data using Apache Iceberg on Amazon S3.
- 📚 Metadata Management: Uses AWS Glue Data Catalog for table and schema management.
- 🔎 Analytical Querying: Enables SQL-based analysis through Amazon Athena.
- ☁️ AWS Cloud Integration: Uses multiple AWS services to build a scalable data pipeline.

AdTech-Streaming-Data-Pipeline/

├── flink/
│   └── stream_processing.py          # Apache Flink streaming job
│
├── glue/
│   └── glue_etl_job.py               # AWS Glue ETL job
│
├── data/
│   └── sample_ad_events.json         # Sample advertisement events
│
├── sql/
│   └── athena_queries.sql            # Analytical queries
│
└── README.md                         # Project documentation

🔧 Technical Components
1. Amazon Kinesis
Amazon Kinesis acts as the real-time ingestion layer.
Advertisement events are continuously sent to the Kinesis stream and made available for downstream stream processing.
2. Apache Flink
Apache Flink processes the incoming streaming events.
The Flink layer is responsible for:
- Consuming events from Kinesis
- Processing streaming records
- Enriching advertisement events
- Preparing events for downstream ETL processing
3. AWS Glue
AWS Glue performs ETL operations on the processed data.
The ETL layer handles:
- Data validation
- Data transformation
- Preparation of curated datasets
- Loading processed data into the analytical storage layer
4. Apache Iceberg
Apache Iceberg provides the table format for the curated datasets stored on Amazon S3.
It provides a structured analytical layer over object storage.
5. AWS Glue Data Catalog
The Glue Data Catalog maintains metadata for the curated datasets and makes them discoverable for analytical services.
6. Amazon Athena
Amazon Athena provides SQL-based analytical querying over the curated data.
🔄 Data Processing Flow
Advertisement Event
        ↓
Amazon Kinesis
        ↓
Apache Flink
        ↓
Event Processing & Enrichment
        ↓
AWS Glue ETL
        ↓
Validation & Transformation
        ↓
Apache Iceberg
        ↓
Amazon S3
        ↓
Glue Data Catalog
        ↓
Amazon Athena
        ↓
Analytical Queries

☁️ AWS Services Used
Service	Purpose
Amazon Kinesis	Real-time event ingestion
Apache Flink	Stream processing and enrichment
AWS Glue	ETL, validation and transformation
Amazon S3	Data storage
Apache Iceberg	Analytical table format
Glue Data Catalog	Metadata management
Amazon Athena	SQL analytics

🎯 Learning Objectives
This project demonstrates:
1. Real-Time Data Processing
2. Stream Ingestion
3. Apache Flink Stream Processing
4. Cloud ETL Pipelines
5. Data Lakehouse Architecture
6. Apache Iceberg
7. AWS Glue Data Catalog
8. Serverless Analytical Querying
9. AWS Data Engineering
10. Streaming-to-Analytics Architecture
💼 Business Value
- Enables near real-time processing of advertisement events.
- Reduces the delay between event generation and analytical availability.
- Creates a structured and queryable data layer.
- Supports scalable advertisement analytics.
- Separates streaming processing from analytical querying.
- Provides a cloud-native architecture for advertising data workloads.
🛠️ Built With
Amazon Kinesis · Apache Flink · AWS Glue · Apache Iceberg · Amazon S3 · AWS Glue Data Catalog · Amazon Athena

## Overview

This project demonstrates an end-to-end Data Engineering solution built on Azure Synapse Analytics using the NYC Taxi & Limousine Commission (TLC) Green Taxi dataset. The primary objective of the project was to gain hands-on experience with different Azure Synapse compute engines, data ingestion patterns, storage formats, and orchestration capabilities while implementing a Medallion Architecture (Bronze, Silver, Gold). The project processes NYC Green Taxi data stored in multiple file formats and transforms it into analytical datasets that can be consumed through Power BI dashboards

## Project Objectives

- Implement ingestion patterns for multiple file formats.
- Configure format-specific readers in Spark and Serverless SQL Pool.
- Standardize different source formats into a unified Parquet-based Medallion Architecture.
- Explore different Azure Synapse compute options:
- Serverless SQL Pool
- Spark Pool
- Implement a Medallion Architecture.
- Create reusable Synapse Pipelines for orchestration.
- Enable analytical consumption using T-SQL.
- Build business-oriented reporting datasets.
- Visualize insights using Power BI.

Note: Multiple compute engines were used as a learning exercise. In production environments, the compute strategy should be selected according to business requirements, performance needs, and cost considerations.

## Dataset

Source: NYC Taxi & Limousine Commission (TLC) Trip Record Data. The project focuses exclusively on Green Taxi trip records.

Data from 2020 and 2021 was purposely selected to expose the ingestion layer to multiple file formats and structures. The objective was to learn and implement format-specific ingestion techniques, schema handling, and data transformation processes within Azure Synapse Analytics. This includeds: 

- CSV
- TSV
- CSV with custom delimiters
- Single-line JSON
- Multi-line (classic) JSON
- Nested JSON
- Parquet
- Delta Lake
- Partitioned folder structures

## Architecture

  ```text
          Source Files
               │
               ▼
          Bronze Layer
               │
               ▼
          Silver Layer
               │
               ▼
           Gold Layer
               │
               ▼
           Power BI
  ```
### Bronze Layer
Objectives
- Ingest raw source data.
- Preserve source data fidelity.
- Implemented Features
- Raw data ingestion from multiple formats.
- Creation of SQL-accessible tables and views.
- Query capabilities through Serverless SQL Pool.

Deliverables
- External tables and views.
- SQL query access through Synapse Serverless SQL Pool.

### Silver Layer

Objectives
Prepare curated datasets optimized for reporting and analytical workloads.

Implemented Features:
- Conversion to Parquet format.
- Datasets stored in Azure Data Lake Storage Gen2.
- Creation of reporting-ready datasets.
- Use of pipelines to keep partitioned data in datasets.
- T-SQL query support.

Deliverables
- Partitioned datasets for eficient query
- Datasets containing key business information required for reporting and dashboarding.

### Gold Layer

The Gold layer contains business-focused datasets designed to answer specific analytical questions. For this project, a Credit Card Campaign analysis dataset was created using the curated Silver layer data.

Deliverables
- Business-ready SQL queries.
- Power BI dashboard.
- Aggregated analytical datasets.
- Dashboard

--------- Add Power BI dashboard screenshot here.

## Orchestration

Synapse Pipelines

The solution uses Synapse Pipelines to orchestrate ingestion and transformation processes.

Pipeline Activities Used:
- Delete Activity
- Script Activity
- Stored Procedure Activity
- ForEach Activity

Pipeline Capabilities

✔ Scheduled execution
✔ Pipeline monitoring
✔ Pipeline failure handling
✔ Pipeline re-execution
✔ Failure alerting

## Analytics & Visualization

### Power BI Integration

A Power BI linked service was configured within Azure Synapse Analytics to integrate reporting capabilities into the Synapse workspace. This allowed Power BI reports to be accessed directly from Synapse Studio while consuming curated datasets exposed through Serverless SQL Pool.

Key capabilities implemented:

- Synapse ↔ Power BI integration.
- DirectQuery connectivity to analytical datasets.
- Embedded report access from Synapse Studio.
- Business reporting based on Gold layer data products.

------- Agrega imagen aqui:

## Future Enhancements

- CI/CD implementation using GitHub Actions.
- Multi-environment deployment (Dev / Prod).
- Infrastructure as Code (Bicep/Terraform).
- Automated testing and validation.
- Parameterized deployments.





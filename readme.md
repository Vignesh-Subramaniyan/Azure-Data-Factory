COVID-19 Data Ingestion & Analytics on Azure Data Factory

This project demonstrates an end-to-end data engineering pipeline for ingesting, transforming, and reporting COVID-19 datasets using Azure Data Services such as ADF, ADLS, Azure SQL, ARM Templates, and Power BI.

📌 Architecture Overview

This solution uses the following Azure components:

Azure Data Factory

Parameterized pipelines

Tumbling Window triggers

Storage event triggers

Linked services for ADLS & Azure SQL

JSON-based datasets

CI/CD with Git integration

Storage

Azure Blob Storage / ADLS Gen2 for raw & curated layers

Azure SQL Database

Stores processed COVID-19 metrics

Acts as serving layer for reporting

Deployment

ARM templates generated through adf_publish branch

Automated provisioning of factory resources

Reporting

Power BI dashboard for COVID-19 trends and metrics

📌 ADF Pipelines Included
1️⃣ tr_ingest_ecdc_data

Fetches raw COVID-19 dataset from the ECDC API.

2️⃣ tr_ingest_population_data

Downloads global population dataset used for per-capita calculations.

3️⃣ tr_process_cases_and_deaths_data

Cleans, transforms, and standardizes COVID-19 cases & deaths data.

4️⃣ tr_process_hospital_admission_data

Aggregates hospital admission metrics for analytics.

5️⃣ tr_sqlize_cases_and_deaths_data

Loads processed datasets into Azure SQL tables for reporting.

📌 Key Features

⏱ Tumbling Window Triggers for scheduled incremental ingestion

📁 Storage Event Triggers for real-time processing

🔧 Parameterized JSON datasets for reusability

🔄 Orchestrated multi-stage pipeline flows

🔐 ADF Git Integration for version control

🚀 ARM Template Deployment for production setups

📁 Folder Structure
/dataset/  
/dataflow/  
/factory/  
/linkedService/  
/pipeline/  
/trigger/  
/adf_publish/     → ARM templates for deployment

📌 Deployment Instructions (Using ARM Templates)

ARM templates are auto-generated under:

/adf_publish/


Deploy using Azure CLI:

az deployment group create \
  --resource-group myRG \
  --template-file ARMTemplateForFactory.json \
  --parameters ARMTemplateParametersForFactory.json

🚀 Ready for Use

This repository can be used as a reference for ADF learning, data engineering projects, cloud analytics, and Power BI reporting.

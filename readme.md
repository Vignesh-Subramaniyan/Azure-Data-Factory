It demonstrates end-to-end COVID-19 data ingestion, transformation, and reporting using Azure Data Services.



📌 Architecture Overview

Azure Data Factory

Pipelines

Tumbling window triggers

Storage event triggers

Parameterized datasets

Azure Blob Storage / ADLS

Azure SQL Database

ARM Deployment Templates

Power BI for reporting

📌 Pipelines in this project

tr_ingest_ecdc_data

Fetches raw COVID-19 dataset from ECDC API

tr_ingest_population_data

Downloads global population dataset

tr_process_cases_and_deaths_data

Cleans & transforms raw COVID cases/deaths

tr_process_hospital_admission_data

Aggregates hospital admission metrics

tr_sqlize_cases_and_deaths_data

Loads transformed data into Azure SQL Tables

📌 Key Features

Tumbling Window Triggers

Storage Event Triggers

Parameterized JSON datasets

Automated pipeline scheduling

ADF Git integration

ARM template deployment folder

📌 Folder Structure
/dataset/  
/dataflow/  
/factory/  
/linkedService/  
/pipeline/  
/trigger/  

📌 How to Deploy?

Use the ARM template inside:

/adf_publish/

Run using:

az deployment group create \
  --resource-group myRG \
  --template-file ARMTemplateForFactory.json \
  --parameters ARMTemplateParametersForFactory.json

# COVID‑19 Reporting with Azure Data Factory

## Overview
This project demonstrates an **end-to-end ETL solution** for COVID‑19 data using **Azure Data Factory (ADF)**.  
It includes pipelines, datasets, linked services, triggers, and ARM templates for deployment.  
The project automates **data ingestion, transformation, and storage**, enabling analytics and reporting.

---

## Repository Structure

covid-reporting-adfvicky/
│
├── globalParameters/ # JSON files defining global parameters for pipelines
├── linkedTemplates/ # Modular ARM templates for pipelines, datasets, triggers
├── ARMTemplateForFactory.json # Main ARM template for deploying ADF factory
├── ARMTemplateParametersForFactory.json # Parameter file for ARM deployment (resource names, connections)
├── readme.md # Project documentation

yaml
Copy code

---

## Folder and File Descriptions

### 1. `globalParameters/`
Contains **JSON files defining global parameters** used across pipelines.  
- Example: API URLs, file paths, environment variables, configurable thresholds.  

### 2. `linkedTemplates/`
Contains **linked ARM templates** for modular deployment.  
- Each template represents pipelines, datasets, triggers, or other ADF components.  
- Enables scalable, organized deployment via the main ARM template.

### 3. `ARMTemplateForFactory.json`
The **primary ARM template** for deploying the Azure Data Factory instance along with its pipelines, datasets, linked services, and triggers.

### 4. `ARMTemplateParametersForFactory.json`
Defines **deployment-specific parameters** for the ARM template, such as:
- Resource names
- Storage account connections
- Pipeline configurations

### 5. `readme.md`
This file, describing the project structure, usage, and deployment instructions.

---

## Deployment Instructions

1. **Clone the repository**

```bash
git clone https://github.com/Vignesh-Subramaniyan/Azure-Data-Factory.git
cd Azure-Data-Factory/covid-reporting-adfvicky
Deploy via ARM Template

Azure Portal:

Navigate to your resource group → Deploy a custom template → Upload ARMTemplateForFactory.json

Use ARMTemplateParametersForFactory.json for parameters.

Azure CLI:

bash
Copy code
az deployment group create \
  --resource-group <YourResourceGroup> \
  --template-file ARMTemplateForFactory.json \
  --parameters @ARMTemplateParametersForFactory.json
Trigger Pipelines

Pipelines can be executed manually via the ADF portal or automatically via triggers defined in linked templates.

Project Highlights
Automated COVID‑19 ETL Pipelines: Ingests, transforms, and stores COVID-19 datasets.

Reusable Components: Modular pipelines, datasets, linked services.

ARM Deployment: Easily deployable using templates.

Scheduled Updates: Triggers ensure daily refresh of COVID data.

Future Enhancements
Connect pipelines to Power BI dashboards for visualizations.

Implement data quality checks and alerting mechanisms.

Add notifications for pipeline failures or data anomalies.


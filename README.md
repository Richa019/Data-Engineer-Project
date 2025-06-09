# Data-Engineer-Project
Tokyo Olympics Data Analysis

This project demonstrates an end-to-end data engineering workflow using Azure Data Factory (ADF), Azure Data Lake Storage (ADLS), Azure Databrick Notebooks, and Azure Synapse Analytics. The pipeline automates data ingestion, cleansing, and analysis using various Azure services.

![image](https://github.com/user-attachments/assets/b7928876-f06a-4690-a447-7ed8120a33e6)

📌 Project Workflow
1. Ingesting Data from GitHub to Azure Data Lake (ADLS) using Azure Data Factory
Utilized Azure Data Factory to orchestrate the data ingestion process.

A Copy Activity was configured in the ADF pipeline:

Source: GitHub (via HTTP connector).

Sink: Azure Data Lake Storage (ADLS Gen2).

Files from GitHub were successfully transferred into a container in ADLS.

2. Data Cleansing in Azure Notebooks
Mounted ADLS to Azure Notebook using a service principal:

Created a Service Principal with proper RBAC (Storage blob data contributor) roles.

Generated client ID, secret, and tenant ID to authenticate notebook access to ADLS.

Loaded data into the notebook from the mounted ADLS path.

Performed data cleansing operations (e.g., removing nulls, standardizing formats, etc.).

Stored the transformed/cleaned data back into ADLS under a new directory( (transformed).

3. Analyzing Data with Azure Synapse Analytics
Set up an Azure Synapse Workspace and attached the same ADLS account as a linked service.

Used datalake in Synapse to query the transformed data directly from ADLS.

Ran analytical queries to extract insights.

Visualized results using Synapse Studio’s built-in visualization tools.





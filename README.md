
# 📊 Tokyo Olympics Data Analysis  
### 🔧 An Azure Data Engineering Project

This project demonstrates an end-to-end data engineering workflow using **Azure Data Factory (ADF)**, **Azure Data Lake Storage (ADLS)**, **Azure Notebooks**, and **Azure Synapse Analytics**. The pipeline automates data ingestion, cleansing, and analysis using various Azure services.

![image](https://github.com/user-attachments/assets/b7928876-f06a-4690-a447-7ed8120a33e6)

---

## 📌 Project Workflow

### 1️⃣ Ingesting Data from GitHub to ADLS using Azure Data Factory

- Utilized **Azure Data Factory (ADF)** to orchestrate the data ingestion process.
- A **Copy Activity** was configured with:
  - **Source:** GitHub (via HTTP connector)
  - **Sink:** Azure Data Lake Storage (ADLS Gen2)
- Files were successfully transferred from GitHub into a staging container in ADLS.

---

### 2️⃣ Data Cleansing in Azure Notebooks

- **Mounted ADLS to Azure Notebook** using a service principal:
  - Created a **Service Principal** with **Storage Blob Data Contributor** role.
  - Generated **Client ID**, **Secret**, and **Tenant ID** for secure access.
- Loaded raw data into the notebook from the mounted ADLS path.
- Performed data cleansing tasks:
  - Standardizing data formats
  - Filtering and transformation
- Stored the transformed data back into ADLS in a new directory (e.g., `/transformed`).

---

### 3️⃣ Data Analysis with Azure Synapse Analytics

- Created a **Synapse Workspace** and linked the same ADLS account as a data source.
- Pulled the transformed data from ADLS using Synapse’s serverless SQL capabilities.
- Ran **analytical queries** to gain insights.
- Utilized **Synapse Studio** to visualize data directly.

---

## 🔐 Authentication and Security

- Implemented a **Service Principal** for secure, programmatic access to ADLS.
- Used **RBAC (Role-Based Access Control)** to restrict access only to required services and users.

---

## 🛠️ Tools & Technologies

| Service                    | Purpose                                        |
|----------------------------|------------------------------------------------|
| **Azure Data Factory**     | Data movement from GitHub to ADLS              |
| **Azure Data Lake Gen2**   | Centralized storage for raw and transformed data |
| **Azure Databricks**        | Data exploration and cleansing via Python      |
| **Azure Synapse Analytics**| Querying and visualizing processed data        |
| **Azure AD**               | Managing service principals and access control |

---

## ✅ Key Learnings

- How to orchestrate pipelines using ADF.
- How to mount and interact with ADLS in notebooks.
- Implementing secure access with service principals.
- Running serverless SQL queries on data lakes.
- Visualization and exploration using Synapse Studio.

---

## 🔗 References

- [Azure Data Factory Documentation](https://learn.microsoft.com/en-us/azure/data-factory/)
- [Mounting ADLS in Notebooks](https://learn.microsoft.com/en-us/azure/databricks/data/data-sources/azure/azure-datalake-gen2)
- [Azure Synapse Analytics](https://learn.microsoft.com/en-us/azure/synapse-analytics/)

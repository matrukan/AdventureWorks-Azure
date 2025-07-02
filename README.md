# 🚀 End-to-End Azure Data Engineering Pipeline using AdventureWorks Dataset

This project presents a complete data engineering solution using Microsoft Azure. It covers the entire lifecycle—from data ingestion to transformation and visualization—using tools like Azure Data Factory, Azure Databricks, Synapse Analytics, and Power BI. The dataset used is [AdventureWorks](https://github.com/microsoft/sql-server-samples/tree/master/samples/databases/adventure-works), a well-known sample business dataset hosted on GitHub.

---

## 🏗️ Architecture Overview

### 1. **Azure Environment Setup**

The following Azure services were provisioned for the pipeline:

- **Azure Data Factory (ADF):** Orchestrates the entire pipeline workflow.
- **Azure Storage Account:** Used as a data lake with three layers—**Bronze** (raw), **Silver** (transformed), and **Gold** (curated).
- **Azure Databricks:** Performs data cleansing and transformation.
- **Azure Synapse Analytics:** Used for querying and structuring data for BI reporting.
- **Power BI:** Consumes curated data for dashboarding and insights.

All components were configured with appropriate IAM roles to ensure secure integration.

---

### 2. **Data Ingestion with Azure Data Factory**

Azure Data Factory serves as the orchestration tool to bring raw data into the data lake.

- A dynamic **Copy Activity** fetches CSV files from GitHub using an HTTP connector.
- Raw data is stored in the **Bronze** container.
- The pipeline is parameterized for flexibility and scalability.

---

### 3. **Data Transformation with Azure Databricks**

Azure Databricks was used to clean, normalize, and structure the ingested data.

**Transformation Steps:**

- Setup a compute cluster for Spark processing.
- Normalize date formats and remove invalid records.
- Aggregate and structure data for analytical consumption.
- Output is stored in **Parquet format** in the **Silver** container for optimized performance.

---

### 4. **Data Modeling with Azure Synapse Analytics**

Using **Synapse Serverless SQL Pools**, data from the Silver layer is structured and prepared for analysis:

- Connected Synapse directly to Parquet files in Azure Data Lake.
- Created databases, schemas, and **external tables/views**.
- Curated data was saved in the **Gold** layer for reporting.

---

### 5. **Business Intelligence with Power BI**

Power BI is used to visualize and deliver insights from the curated dataset.

- Connected to Synapse for real-time data analysis.
- Developed interactive dashboards tailored for stakeholders and decision-makers.

---

## ✅ Key Benefits

This project highlights the strength of the Azure ecosystem in building robust, scalable data engineering solutions:

- 🔄 **Automation**: Fully automated data flow from ingestion to reporting.
- ⚡ **Performance**: Optimized transformations and querying using Spark & Parquet.
- 🧩 **Modularity**: Separation of concerns via Bronze/Silver/Gold architecture.
- 📊 **Insights**: Interactive BI dashboards empower decision-makers with data.

---

## 🙌 Acknowledgments

Special thanks to [Ansh Lamba](https://github.com/anshlambagit) for his open-source contributions and detailed walkthroughs. Check out his [YouTube video guide](https://www.youtube.com/watch?v=0GTZ-12hYtU&t=15907s&ab_channel=AnshLamba) for an in-depth tutorial that inspired this project.

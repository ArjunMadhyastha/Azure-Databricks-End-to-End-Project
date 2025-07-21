# End-to-End Data Pipeline on Azure & Databricks with Medallion Architecture

## Overview
This project demonstrates an enterprise-grade, end-to-end data pipeline on **Azure** and **Databricks**, implementing the **Medallion Architecture (Bronze → Silver → Gold)** with real-time streaming, data transformations, and Slowly Changing Dimensions (SCD1 & SCD2) handling.

It showcases best practices in building scalable, governed, and reliable data pipelines using cloud-native tools.

![Pipeline](https://github.com/ArjunMadhyastha/Azure-Databricks-End-to-End-Project/blob/39237d67896ea10d6198839f3cd86052b6140a46/End%20to%20End%20Pipeline.png)
---

##  Architecture
###  Technologies Used:
- **Azure Storage Account** (ADLS Gen2) — for raw & processed data storage
- **Azure Containers** — separate containers for `bronze`, `silver`, `gold`
- **Azure Databricks**
  - Unity Catalog for governance
  - Delta Lake & Delta Live Tables
  - PySpark for transformations
  - Structured Streaming for ingestion
- **Medallion Architecture**
  - Bronze: Raw data (streaming)
  - Silver: Cleaned & transformed data
  - Gold: Analytics-ready data with SCD1 & SCD2 applied

---

## Workflow
1️⃣ **Provision Azure resources**
- Created a **Storage Account** and containers: `bronze`, `silver`, `gold`.
- Uploaded raw data to the `bronze` container.

2️⃣ **Set up Databricks**
- Created a Databricks workspace in Azure.
- Created an **Access Connector** to securely connect Databricks to the Storage Account.

3️⃣ **Configure Unity Catalog**
- Set up a Metastore for governance.
- Created catalogs, schemas, and managed tables.

4️⃣ **Ingest & Transform Data**
- Streamed data from the `bronze` container into Databricks.
- Processed & cleaned data using **PySpark** in the **Silver Layer**.
- Applied **SCD1 & SCD2** in the **Gold Layer** for slowly changing dimensions.

5️⃣ **Build Pipeline**
- Orchestrated the entire flow into an end-to-end pipeline ready for analytics and BI consumption.

---


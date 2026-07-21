# 🚚 End-to-End Supply Chain Cloud Analytics Platform

[![Azure SQL](https://img.shields.io/badge/Azure%20SQL-Database-blue?logo=microsoftazure)](https://azure.microsoft.com/en-us/products/azure-sql/database/)
[![Power BI](https://img.shields.io/badge/Power%20BI-Dashboards-F2C94C?logo=powerbi)](https://powerbi.microsoft.com/)
[![T-SQL](https://img.shields.io/badge/T--SQL-Data%20Modeling-CC292B)](https://docs.microsoft.com/en-us/sql/t-sql/)

> An enterprise-grade, cloud-native analytics solution transforming raw transactional supply chain data into high-performance analytical models and executive dashboards.

---

## 📌 Executive Summary

This repository demonstrates an **end-to-end Data Engineering & Business Intelligence (BI) project** built on Microsoft Azure. The solution ingests raw transactional datasets from Azure Blob Storage, models them into a multi-layered Star Schema (Medallion Architecture), executes advanced T-SQL analytical workloads, and delivers interactive visual reports in Power BI.

### 🏗️ Architecture & Data Pipeline
`Azure Blob Storage (Bronze)` ➔ `T-SQL BULK INSERT` ➔ `Azure SQL Database (Silver - Star Schema)` ➔ `T-SQL Analytics` ➔ `Power BI Dashboard`

---

## 🛠️ Key Technical Highlights

* **Cloud Data Ingestion:** Automated high-throughput ingestion from Azure Blob Storage into Azure SQL using SAS Token Credentials and `BULK INSERT`.
* **Dimensional Modeling:** Architected a 3NF normalized-to-Star Schema data model featuring Fact (`fact_orders`) and Dimension tables (`dim_products`, `dim_customers`, `dim_hubs`, `dim_shipping_locations`).
* **Advanced T-SQL Analytics:** Solved complex business queries including **Gaps & Islands streak detection**, **Cohort Retention Analysis**, **RFM Customer Segmentation**, and **Top-N Product Performance** using CTEs and Window Functions (`ROW_NUMBER`, `RANK`, `SUM() OVER()`).
* **Executive BI Dashboards:** Built DirectQuery/Import Power BI reporting layers focused on Logistics SLA breaches, revenue shares, and profitability margins.

---

## 🧰 Tech Stack

| Layer | Technology |
|---|---|
| **Cloud Storage** | Azure Blob Storage (Container Landing Zone) |
| **Database Engine** | Azure SQL Database |
| **Development Environment** | VS Code (macOS) with `mssql` & `Azure Account` extensions |
| **Language & Queries** | T-SQL (DDL, DML, Window Functions, CTEs, Indexing) |
| **Visualization** | Power BI Desktop |

---

## 🚦 Getting Started
To initialize and populate the entire Data Warehouse, follow the execution order below:

1. **Create Schemas & Database:** Run the script: [database_initialization.sql](./scripts/database_initialization.sql)
2. **Create Tables:** Run scripts respectively:
   - [1_bronze_ddl](./scripts/bronze/bronze_ddl.sql)
   - [2_silver_ddl](./scripts/silver/silver_ddl.sql)
   - [3_gold_ddl](./scripts/gold/gold_ddl.sql)
4. **Create Stored Procedures:** Run scripts respectively:
   - [1_bronze_data_load_procedure](./scripts/bronze/bronze_data_load_procedure.sql)
   - [2_silver_data_load_procedure](./scripts/silver/silver_data_load_procedure.sql)
   - [3_gold_data_load_procedure](./scripts/gold/gold_data_load_procedure.sql)
5. **Load Raw Data:**
   ```sql
   CALL bronze.sp_load_bronze();
6. **Transform to Silver:**
   ```sql
   CALL silver.sp_load_silver();
7. **Finalize Gold Schema:**
   ```sql
   CALL gold.sp_load_gold();

---

## 🌟 About Me
I am a **Data Analytics enthusiast**, transforming data into actionable business insights 🔎

* **Looking for:** Junior Data Analyst roles.
* **Tech I love:** SQL, Excel, Tableau, Power BI

📫 **Let's connect:** https://www.linkedin.com/in/rafal-rydzkowski-data/ | RafalRydzkowskiJ@gmail.com

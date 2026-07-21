# 🚚 End-to-End Supply Chain Cloud Analytics Platform

[![Azure SQL](https://img.shields.io/badge/Azure%20SQL-Database-blue?logo=microsoftazure)](https://azure.microsoft.com/en-us/products/azure-sql/database/)
[![Power BI](https://img.shields.io/badge/Power%20BI-Dashboards-F2C94C?logo=powerbi)](https://powerbi.microsoft.com/)
[![T-SQL](https://img.shields.io/badge/T--SQL-Data%20Modeling-CC292B)](https://docs.microsoft.com/en-us/sql/t-sql/)

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

Execute the T-SQL scripts in `SQL_scripts/` sequentially to build and populate the Medallion layers:

### 1. Bronze Layer Deployment (Raw Landing)
**`1_bronze_ddl.sql`** -> **`1_bronze_load.sql`** -> **`1_bronze_check.sql`**

### 2. Silver Layer Deployment (Star Schema)
**`2_silver_ddl.sql`** -> **`2_silver_load.sql`** -> **`2_silver_check.sql`**

### 3. Analytics Layer (Business Reporting)
Execute **`sql_scripts/business_questions.sql`** to run advanced analytical queries.

### 4. Power BI Dashboard Integration
1. Open Power BI Desktop.
2. Connect to the Azure SQL Database instance using the **SQL Server Database** connector.
3. Import the `silver` Star Schema tables or query views.
4. Open the `.pbix` file located in the `/powerbi_dashboard` directory to interact with the executive report.

---

## 🌟 About Me
I am a **Data Analytics enthusiast**, transforming data into actionable business insights 🔎

* **Looking for:** Junior Data Analyst roles.
* **Tech I love:** SQL, Excel, Tableau, Power BI

📫 **Let's connect:** https://www.linkedin.com/in/rafal-rydzkowski-data/ | RafalRydzkowskiJ@gmail.com

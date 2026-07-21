# 🚚 End-to-End Supply Chain Cloud Analytics Platform

[![Azure SQL](https://img.shields.io/badge/Azure%20SQL-Database-blue?logo=microsoftazure)](https://azure.microsoft.com/en-us/products/azure-sql/database/)
[![Power BI](https://img.shields.io/badge/Power%20BI-Dashboards-F2C94C?logo=powerbi)](https://powerbi.microsoft.com/)
[![T-SQL](https://img.shields.io/badge/T--SQL-Data%20Modeling-CC292B)](https://docs.microsoft.com/en-us/sql/t-sql/)

> An enterprise-grade, cloud-native analytics solution transforming raw transactional supply chain data into high-performance analytical models and executive dashboards.

---

## 📌 Executive Summary

This repository demonstrates an **end-to-end Data Engineering & Business Intelligence (BI) project** built on Microsoft Azure. The solution ingests raw transactional datasets from Azure Blob Storage, models them into a multi-layered Star Schema (Medallion Architecture), executes advanced T-SQL analytical workloads, and delivers interactive visual reports in Power BI.

### 🏗️ Architecture & Data Pipeline
`Azure Blob Storage (Bronze)` ➔ `T-SQL BULK INSERT` ➔ `Azure SQL Database (Silver - Star Schema)` ➔ `T-SQL Analytics (Gold)` ➔ `Power BI Dashboard`

---

## 🛠️ Key Technical Highlights

* **Cloud Data Ingestion:** Automated high-throughput ingestion from Azure Blob Storage into Azure SQL using SAS Token Credentials and `BULK INSERT` with `TABLOCK` optimizations.
* **Dimensional Modeling:** Architected a 3NF normalized-to-Star Schema data model featuring Fact (`fact_orders`) and Dimension tables (`dim_products`, `dim_customers`, `dim_hubs`, `dim_shipping_locations`).
* **Performance Tuning & Indexing:** Implemented Nonclustered Indexes and SARGable date filtering to prevent full table scans and minimize I/O overhead on Azure SQL Database.
* **Advanced T-SQL Analytics:** Solved complex business queries including **Gaps & Islands streak detection**, **Cohort Retention Analysis**, **RFM Customer Segmentation**, and **Top-N Product Performance** using CTEs and Window Functions (`ROW_NUMBER`, `DENSE_RANK`, `NTILE`, `SUM() OVER()`).
* **Executive BI Dashboards:** Built DirectQuery/Import Power BI reporting layers focused on Logistics SLA breaches, revenue shares, and profitability margins.

---

## 🧰 Tech Stack

| Layer | Technology |
|---|---|
| **Cloud Storage** | Azure Blob Storage (Container Landing Zone) |
| **Database Engine** | Azure SQL Database (Serverless Tier) |
| **Development Environment** | VS Code (macOS) with `mssql` & `Azure Account` extensions |
| **Language & Queries** | T-SQL (DDL, DML, Window Functions, CTEs, Indexing) |
| **Visualization** | Power BI Desktop & Service |

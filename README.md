# 🛍️ E-commerce Event-Driven Data Pipeline

## 🧾 Project Overview
This project implements a **comprehensive event-driven data pipeline** for e-commerce transactional data processing using **Databricks**, **PySpark**, and **Delta Lake**.  
It handles multiple data sources with advanced **data engineering patterns** such as **SCD2 (Slowly Changing Dimensions)**, **data validation**, **data enrichment**, and **automated archiving**.

---

## ⚙️ Tech Stack
- 💻 **Databricks** – Cloud-based data processing platform  
- 🔥 **PySpark** – Distributed data processing engine  
- 🧊 **Delta Lake** – ACID transactions and versioning for data lakes  
- 📦 **Databricks Volumes** – Managed storage for file-based data sources  
- 🧠 **Databricks Workflows** – Job orchestration and scheduling  
- 🧰 **GitHub** – Version control and CI/CD integration  

---

## 🗂️ Project Structure

Ecomm_Event_Driven_Datapipeline/
├── data/
│   ├── customers_2025_01_15.csv
│   ├── customers_2025_01_16.csv
│   ├── inventory_2025_01_15.csv
│   ├── inventory_2025_01_16.csv
│   ├── orders_2025_01_15.csv
│   ├── orders_2025_01_16.csv
│   ├── products_2025_01_15.csv
│   ├── products_2025_01_16.csv
│   ├── shipping_2025_01_15.csv
│   ├── shipping_2025_01_16.csv
│   ├── trigger_2025_01_15.json
│   └── trigger_2025_01_16.json
└── notebook/
    ├── 01_orders_stage_load.ipynb
    ├── 02_customers_stage_load.ipynb
    ├── 03_products_stage_load.ipynb
    ├── 04_inventory_stage_load.ipynb
    ├── 05_shipping_stage_load.ipynb
    ├── 06_data_validation.ipynb
    ├── 07_data_enrichment.ipynb
    └── 08_final_merge_operation.ipynb

---

## 🧱 Pipeline Architecture

### 🔹 1. Data Ingestion Layer
- 📄 **Source Files**: CSV files for orders, customers, products, inventory, and shipping  
- 🧾 **Trigger Files**: JSON files that initiate batch processing automatically  
- 🗃️ **Storage**: Databricks Volumes for managed file storage  

### 🔹 2. Data Processing Layer
- ⚙️ **Stage Load Notebooks**: Load and validate raw data  
- 🧮 **Validation Notebook**: Apply cross-reference and business rules  
- ✨ **Enrichment Notebook**: Add business metrics and analytics  
- 🔁 **Merge Notebook**: Apply SCD2 for historical versioning  

### 🔹 3. Data Storage Layer
- 🧱 **Staging Tables**: Temporary validated data  
- 🧾 **Target Tables**: Historical versioned data using Delta Lake  
- 📊 **Analytics Tables**: For BI and reporting  

---

## 📘 Notebook Details

### 🧾 01_orders_stage_load.ipynb
- Loads order data  
- Validates order amounts, customer & product IDs  
- Archives processed files  
- Logs processing summary  

### 👥 02_customers_stage_load.ipynb
- Processes customer demographic data  
- Validates email & phone formats  
- Calculates customer age and lifecycle stage  
- Enriches with customer segments  

### 📦 03_products_stage_load.ipynb
- Loads product catalog data  
- Validates product IDs and pricing  
- Handles product hierarchy and categories  

### 🏬 04_inventory_stage_load.ipynb
- Tracks stock availability  
- Detects anomalies in stock levels  
- Updates warehouse-level inventory  

### 🚚 05_shipping_stage_load.ipynb
- Loads shipment and delivery data  
- Tracks order status, delays, and carrier details  

### 🧪 06_data_validation.ipynb
- Cross-validates across tables (e.g., Order-Customer-Product links)  
- Ensures referential integrity  
- Logs failed validations to an audit table  

### ✨ 07_data_enrichment.ipynb
- Adds calculated KPIs like total revenue, margin, delivery SLA  
- Joins with product and customer attributes for analytics  

### 🔁 08_final_merge_operation.ipynb
- Implements **SCD Type 2** for historical tracking  
- Merges incremental data into master Delta tables  
- Updates audit logs and archival layers  

---

## 🧩 Key Features
- 🔔 **Event-driven** batch processing with trigger JSONs  
- 🧾 **Schema validation** and error handling  
- 🧠 **SCD2 history tracking** for dimension tables  
- 📂 **Automatic archiving** of processed source files  
- 🔄 **Reprocessing support** for failed batches  
- 🧰 **Fully orchestrated via Databricks Workflows**

---

## 🚀 Future Enhancements
- 🪣 Migrate file ingestion to **Autoloader** for streaming  
- 🧠 Add **ML model** for sales prediction  
- 🧾 Implement **Data Quality checks** using **Deequ or Great Expectations**  
- ☁️ Integrate with **Power BI or Qlik** for visualization  

---

## 🏁 Summary
This pipeline demonstrates how **Databricks + PySpark + Delta Lake** can be used to build a **scalable, maintainable, and event-driven data architecture** for e-commerce platforms.


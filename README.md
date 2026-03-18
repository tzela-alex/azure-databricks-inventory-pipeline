# azure-databricks-inventory-pipeline
End-to-End Data Pipeline using PySpark and Azure Blob Storage
Azure Databricks Data Pipeline: Warehouse Inventory Optimization

📌 Project Overview
This project simulates a real-world Data Engineering pipeline. It processes raw, "dirty" inventory and supplier data, applies data quality rules, and transforms it into an aggregated, reporting-ready dataset (Gold Layer) suitable for Business Intelligence tools like Power BI.

🛠️ Tech Stack
Cloud Storage: Azure Blob Storage (WASBS)

Compute / Processing: Azure Databricks

Language / Framework: Python, PySpark

Architecture: Medallion Architecture (Bronze, Silver, Gold)

🏗️ Pipeline Architecture (Medallion Approach)
Bronze Layer (Raw Data Ingestion): * Extracted raw .csv files (containing missing dates, negative quantities, and duplicates) directly from an Azure Blob Storage container (raw folder).

Silver Layer (Data Cleaning & Enrichment): * Used PySpark to filter out negative inventory quantities (Data Quality rule).

Handled NULL values and dropped duplicate records.

Performed a LEFT JOIN between Inventory and Suppliers data to enrich the dataset with contact information.

Gold Layer (Aggregation & Presentation): * Aggregated the data using groupBy to calculate the Total Inventory Quantity and Number of Restocks per product.

Automatically loaded the final, clean DataFrame back into the Azure Blob Storage (processed folder) as a consolidated file, ready for BI consumption.

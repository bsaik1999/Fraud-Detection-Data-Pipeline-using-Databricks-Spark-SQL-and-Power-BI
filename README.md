# Fraud Detection Data Pipeline using Databricks, Spark SQL, and Power BI

## Project Overview

This project builds a comprehensive fraud detection data pipeline leveraging Databricks and Spark SQL for data engineering and Power BI for visualization. It uses a large transactional dataset to detect and analyze fraudulent transactions across multiple dimensions such as geography, merchant categories, time, and customer profiles. The goal is to provide actionable insights into fraud patterns and hotspots to support risk mitigation efforts.

---

## Data Description

- **fraud_train_cleaned**: The core dataset containing over 1 million transaction records, cleaned and preprocessed, including fields such as transaction timestamp, credit card number, merchant info, transaction amount, customer demographics, geographic coordinates, and a binary fraud label.
- **fraud_test**: A similar dataset reserved for model evaluation or further analysis.
- **Auxiliary datasets**: Include merchant category codes, city/population data, and fraud labels for enriching analysis.

---

## Project Workflow

### 1. Data Ingestion & Cleaning
- Imported raw CSV data into Databricks.
- Cleaned and transformed data using Spark SQL and PySpark: handled missing values, formatted timestamps, and standardized fields.
- Created a cleaned fact table (`fraud_train_cleaned`) as the base for downstream analysis.

### 2. Data Engineering & Modeling
- Designed and created dimension tables (`DimCustomer`, `DimMerchant`, `DimGeography`, `DimTime`) to implement a star schema for efficient querying.
- Built aggregated views such as fraud rate by category, state, and hour of the day to support quick analysis.
- Created summary tables to enable easy drill-downs and slicing in visualization tools.
- Developed ETL pipelines in Databricks notebooks using SQL and PySpark for seamless data transformation and aggregation.

### 3. Fraud Analysis & Insights
- Analyzed fraud trends across multiple dimensions:
  - Fraud percentage by state and city to identify high-risk areas.
  - Temporal fraud trends to detect suspicious spikes in certain hours or days.
  - Merchant and customer profiling to uncover risky merchants and demographics.
- Generated geospatial fraud hotspots using latitude and longitude data for granular location-based analysis.

### 4. Visualization & Reporting (Power BI)
- Connected Power BI directly to Databricks SQL endpoints for live querying.
- Developed interactive dashboards showing:
  - Choropleth maps of fraud percentages by state.
  - Line charts for fraud and transaction volume trends over time.
  - Bar charts and tables listing top risky merchants and customer segments.
  - Geospatial bubble maps pinpointing fraud hotspots by merchant location.
- Enabled filtering, tooltip details, and drill-down features for end-user exploration.

### 5. Version Control & Collaboration
- Saved all Databricks notebooks (SQL and PySpark) and Power BI files in a structured GitHub repository.
- Used Git Large File Storage (LFS) to manage large Power BI `.pbix` files effectively.
- Followed best practices to organize code and documentation for reproducibility and future enhancements.

---

## How to Use This Project

1. **Databricks Setup**  
   - Import notebooks into your Databricks workspace.  
   - Load the provided datasets or connect to your own fraud transaction data.  
   - Run the SQL and PySpark cells sequentially to create tables, views, and dimension models.

2. **Power BI Setup**  
   - Use the Databricks SQL Warehouse credentials and access tokens to connect Power BI to Databricks.  
   - Open the provided `.pbix` file or create new reports based on the exposed views and tables.  
   - Explore fraud patterns, customize filters, and publish dashboards to share with stakeholders.

3. **GitHub Repo**  
   - Clone the repo to access all code, notebooks, and reports.  
   - Use Git LFS for handling large files (like Power BI reports).  
   - Contribute improvements by submitting pull requests.

---

## Technologies Used

- **Databricks**: Unified analytics platform for ETL and SQL querying.
- **Apache Spark (SQL & PySpark)**: Distributed processing for large-scale data transformation.
- **Power BI**: Business Intelligence tool for interactive dashboards and visualization.
- **Git & Git LFS**: Version control system and large file management.
- **Python**: For notebook scripting and data preprocessing.

---

## Project Highlights

- Handling 1 million+ transaction records efficiently with Spark SQL.
- Implementing star schema data modeling for fraud analytics.
- Leveraging geospatial data to detect fraud hotspots.
- Real-time Power BI dashboard integration with Databricks SQL.
- End-to-end reproducible fraud detection pipeline with version control.

---

## Future Work

- Integrate machine learning models to predict fraud likelihood in real-time.
- Automate ETL workflows using Databricks Jobs or Apache Airflow.
- Implement alerting mechanisms for unusual fraud spikes.
- Expand dashboards with customer segmentation and behavior analytics.




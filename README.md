# Agriculture-Crop-RDD

# Agricultural Crop Production & Yield Optimization Analytics System

## Project Overview
This project implements an **end-to-end agricultural analytics pipeline** to analyze crop production and yield performance across different regions, seasons, and years. The system automates data ingestion, cleaning, transformation, and analytics using Databricks and PySpark, and presents insights through Power BI dashboards.

The goal is to enable **data-driven agricultural decision-making** by identifying production trends, high-yield regions, seasonal performance, and productivity insights.

---

# Architecture

Raw Crop Dataset (CSV)
│
▼
01_data_ingestion_bronze (Databricks Notebook)
│
▼
02_data_cleaning_silver (Data Cleaning & Validation)
│
▼
03_yield_transformation_gold (Yield Calculation)
│
▼
04_crop_analytics (PySpark Analytics)
│
▼
Analytics Tables (Databricks SQL)
│
▼
Power BI Dashboards


The project follows the **Medallion Architecture (Bronze → Silver → Gold)** to structure the data pipeline.

---

# Technology Stack

| Category | Tools |
|--------|------|
| Data Processing | Python, Pandas, NumPy |
| Big Data Processing | PySpark |
| Platform | Databricks |
| Workflow Orchestration | Databricks Workflows |
| Data Storage | Parquet / Delta Lake |
| Visualization | Power BI |
| Version Control | Git & GitHub |

---

# Project Modules

## 1. Data Ingestion (Bronze Layer)

Loads raw crop production data into Databricks.

**Tasks**
- Read raw CSV dataset
- Validate schema and structure
- Convert dataset into Spark DataFrame
- Store raw data in Parquet format

**Notebook**
01_data_ingestion_bronze.ipynb

**Output**
dbfs:/crop/bronze/crop_raw


---

## 2. Data Cleaning (Silver Layer)

Prepares the dataset for analytics.

**Tasks**
- Remove duplicate records
- Handle missing values
- Normalize crop names, states, and seasons
- Validate production and area fields

**Notebook**

02_data_cleaning_silver.ipynb

**Output**

dbfs:/crop/silver/crop_clean


---

## 3. Yield Transformation (Gold Layer)

Calculates crop productivity metrics.

**Formula**

Yield = Production / Area


**Tasks**
- Compute yield for each crop
- Handle division errors
- Prepare analytics-ready dataset

**Notebook**

03_yield_transformation_gold.ipynb


**Output**

dbfs:/crop/gold/crop_yield


---

## 4. Crop Analytics

Performs large-scale analytics using PySpark.

**Analytics Performed**

- Crop production trends
- Seasonal yield performance
- State-wise productivity ranking
- Identification of low-yield regions
- Year-over-year production comparison

**Notebook**

04_crop_analytics.ipynb


**Outputs**

crop_trend
state_yield
season_performance


---

# Workflow Automation

The pipeline is orchestrated using **Databricks Workflows**, which automates the execution of all notebooks.

**Pipeline Flow**

01_data_ingestion
↓
02_data_cleaning
↓
03_yield_transformation
↓
04_crop_analytics


The workflow supports scheduling, retries, and monitoring.

---

# Visualization

Power BI dashboards are created to provide interactive insights.

**Dashboard Features**

- Crop production trends across years
- State-wise yield comparison
- Seasonal productivity analysis
- Agricultural KPI metrics

**Key KPIs**

- Total Production
- Average Yield
- Top Performing State
- Top Producing Crop

---

# Data Validation

The system includes validation checks such as:

- Missing value detection
- Duplicate record removal
- Invalid production or area values
- Incorrect yield calculations

---

# Repository Structure

Agriculture_Crop_Analytics
│
│01_data_ingestion_bronze.ipynb
│02_data_cleaning_silver.ipynb
│03_yield_transformation_gold.ipynb
│04_crop_analytics.ipynb
│
├── production.csv
│ 
└── README.md



---

# Key Insights

This analytics system helps identify:

- High-performing crops across regions
- Seasonal variations in agricultural productivity
- Low-yield regions requiring attention
- Long-term production trends

These insights support **agricultural planning, policymaking, and resource optimization**.

---

# Future Enhancements

Possible improvements include:

- Machine learning models for crop yield prediction
- Integration with weather and soil datasets
- Real-time agricultural monitoring
- Delta Lake optimization for large-scale datasets

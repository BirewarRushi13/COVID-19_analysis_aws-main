# 🦠 COVID-19 Data Engineering Pipeline using AWS & Python

This project is a end-to-end **Data Engineering pipeline** built with  
**AWS Athena, AWS Glue, Amazon S3, Amazon Redshift, and Python (pandas + boto3)**.

The goal is to take COVID-19 datasets from AWS public data lake, clean them
with Python, organize them into a **Star Schema (Fact + Dimension tables)**, and store
them in cloud services for BI dashboards and analytics.

This project shows how real data engineers build pipelines using cloud tools.

## 📌 Project Overview

1. **Extract**  
   Get COVID-19 datasets from AWS Athena (public AWS COVID data).

2. **Transform**  
   Use Python and pandas to clean data and create:

3. **Load**  
   Upload cleaned tables into AWS S3 as CSV files.

4. **Data Warehouse Setup**  
   Create tables inside Amazon Redshift with **Star Schema** design.

5. ** Final Step**  
   Load S3 data into Redshift using `COPY` commands (for BI tools like Power BI).

## 🛠️ Technologies Used

### **AWS Services**
- **Amazon Athena** → Query public COVID-19 datasets  
- **AWS Glue** → Data catalog (tables + schema)  
- **Amazon S3** → Store cleaned CSVs  
- **Amazon Redshift** → Data warehouse for BI  

### **Python Tools**
- **pandas** → Cleaning & transformation  
- **boto3** → AWS connection (S3, Glue, Athena)  
- **Jupyter Notebook** → Development environment  

## ⭐ Pipeline Architecture

Athena (Query Public COVID Data)
↓
Python (pandas cleaning + transformations)
↓
Build Star Schema Tables (fact + dimensions)
↓
Store Clean Tables in Amazon S3
↓
Create Data Warehouse Tables in Redshift
↓
Load S3 → Redshift via COPY
↓
BI Dashboard (Power BI / QuickSight)

## 📊 Star Schema Design

### **Fact Table**
- `factCovid`  
  Stores main COVID metrics: date, region, cases, deaths, hospital data.

### **Dimension Tables**
- `dimDate` → year, month, weekday  
- `dimRegion` → state, country, location info  
- `dimHospitalBeds` → hospital bed capacity data  

This structure makes analytics fast and simple.

## 📘 Notebook Summary (Python script)

Inside **Covid19Project.ipynb**, the notebook:

1. Connects to Athena using boto3  
2. Runs SQL queries to extract COVID datasets  
3. Loads the results into pandas  
4. Cleans column names and data types  
5. Builds fact and dimension tables  
6. Uploads these tables to S3  
7. Creates Redshift tables using SQL DDL  
8. Provides COPY commands for loading data (future step)

## 🚀 Future Improvements

- Automate the pipeline using AWS Lambda or Glue Jobs  
- Add visualizations (matplotlib / seaborn)  
- Connect Redshift to QuickSight or Power BI  
- Add error handling and logging  
- Convert notebook into production-ready Python scripts 

# 🍽️ Swiggy Sales Analytics Dashboard Microsoft Fabric & Power BI

<p align="center">
  <img src="https://img.shields.io/badge/Microsoft%20Fabric-Data%20Engineering-blue?style=for-the-badge&logo=microsoftfabric" alt="Microsoft Fabric"/>
  <img src="https://img.shields.io/badge/Power%20BI-Interactive%20Dashboard-yellow?style=for-the-badge&logo=powerbi" alt="Power BI"/>
  <img src="https://img.shields.io/badge/SQL-T--SQL-orange?style=for-the-badge&logo=microsoftsqlserver" alt="SQL"/>
  <img src="https://img.shields.io/badge/Project-Completed-success?style=for-the-badge" alt="Project Status"/>
</p>

<p align="center">
  <b>📊 Business Intelligence | ⚙️ Data Engineering | 📈 Sales Analytics</b>
</p>

An end-to-end **Swiggy Sales Analytics Dashboard** built using **Microsoft Fabric, Fabric Lakehouse, Fabric Warehouse, T-SQL, and Power BI** to analyze order performance, sales trends, restaurant ratings, and geographical patterns.

This project combines data engineering and business intelligence to transform raw data into structured analytical datasets and interactive dashboards that support data-driven decision-making.

---

## 📌 Table of Contents

- 🎯 Project Overview
- 📊 Dashboard Highlights
- 📈 Key Performance Indicators
- 📉 Visualizations and Analysis
- 🎛️ Interactive Features
- 🛠️ Technology Stack
- 🏗️ Project Architecture
- 🗄️ Data Model
- 💻 SQL Development
- 🖼️ Dashboard Preview
- 📁 Repository Structure
- 🚀 How to Explore the Project
- 🧠 Skills Demonstrated
- 👩‍💻 Author

---

## 🎯 Project Overview

The objective of this project is to develop an interactive Power BI dashboard that provides insights into Swiggy's restaurant and order data.

The solution uses Microsoft Fabric to manage data ingestion, transformation, storage, and analytical modeling before connecting the prepared data to Power BI for visualization.

### Business Objectives

- Monitor overall order and sales performance.
- Analyze restaurant ratings and customer feedback indicators.
- Identify sales and order trends over time.
- Compare performance across geographical locations.
- Explore restaurant and dish-level performance.
- Improve data reliability through SQL-based validation and duplicate management.

---

## 📊 Dashboard Highlights

The dashboard is designed to provide a consolidated view of Swiggy business performance through KPI cards, charts, comparisons, and interactive filters.

### Main Dashboard Components

- **Executive Overview:** High-level KPIs for quick performance monitoring.
- **Sales Analysis:** Sales distribution and performance comparisons.
- **Order Analysis:** Order volume and time-based trends.
- **Restaurant Analysis:** Restaurant-level performance and rating comparisons.
- **Location Analysis:** Geographical comparisons of orders and sales.
- **Rating Analysis:** Average ratings and rating-count indicators.

*The final sections and visuals should reflect the pages included in your actual Power BI report.*

---

## 📈 Key Performance Indicators (KPIs)

The dashboard can display the following business metrics, depending on the measures available in the report.

| KPI | Business Purpose |
|---|---|
| 💰 Total Sales | Measures the total recorded sales value |
| 📦 Total Orders | Tracks the number of orders |
| ⭐ Average Rating | Evaluates the average recorded restaurant rating |
| 📝 Rating Count | Measures the number of recorded ratings |
| 📍 Location Performance | Compares business performance across locations |
| 📅 Sales Trends | Tracks changes in sales across dates or periods |

### Example DAX Measures

Use these examples only after confirming that your table and column names match your Power BI model.

**Total Orders**
```dax
Total Orders = DISTINCTCOUNT(fact_order[order_id])
```

**Total Sales**

```dax
Total Sales = SUM(fact_order[sales])
```

**Average Rating**

```dax
Average Rating = AVERAGE(fact_order[rating])
```

**Rating Count**

```dax
Rating Count = COUNT(fact_order[rating])
```

*Note: Replace column names with the actual fields in your model. Use `SUM` for sales only when the sales column contains an additive order-level amount. Confirm the grain of the fact table to avoid double-counting.*

---

## 📉 Visualizations and Analysis

The dashboard can include the following visual types to make business performance easier to understand.

| Visualization | Purpose |
|---|---|
| KPI Cards | Display important business metrics |
| Line Chart | Show sales and order trends over time |
| Bar Chart | Compare sales or orders across locations |
| Donut Chart | Show category or location distribution |
| Table/Matrix | Provide detailed restaurant or order analysis |
| Slicers | Filter data by date, location, restaurant, or category |

These visuals help users explore business performance at both summary and detailed levels.

---

## 🎛️ Interactive Dashboard Features

- 📅 Date-based filtering for period-wise analysis.
- 📍 Location slicers for geographical comparisons.
- 🍽️ Restaurant and dish-level filtering, where supported by the data model.
- 🔎 Cross-filtering between compatible charts.
- 📊 KPI cards for quick performance monitoring.
- 📋 Detailed views for exploring underlying records.
- 🔄 Dynamic report updates when supported filters or selections change.

---

## 🛠️ Technology Stack

| Technology | Purpose |
|---|---|
| Microsoft Fabric | Unified data engineering and analytics |
| Fabric Lakehouse | Data storage and preparation |
| Fabric Warehouse | Structured analytical data storage |
| T-SQL | Data validation, queries, and duplicate management |
| ETL Pipelines | Data movement and workflow orchestration |
| Power BI | Interactive dashboards and reporting |
| DAX | Measures and KPI calculations |
| Power Query | Data transformation, where used |

---

## 🏗️ Project Architecture

```text
📂 Source Swiggy Data
         |
         ▼
🏞️ Microsoft Fabric Lakehouse
         |
         ▼
🧹 Data Cleaning & Transformation
         |
         ▼
🔄 Lakehouse-to-Warehouse Pipeline
         |
         ▼
🏢 Microsoft Fabric Warehouse
         |
         ├── dim_date
         ├── dim_location
         ├── dim_restaurant (if implemented)
         ├── dim_dish (if implemented)
         |
         └── fact_order
                  |
                  ▼
          📊 Power BI Data Model
                  |
                  ▼
          📈 Swiggy Analytics Dashboard
                  |
                  ▼
          💡 Business Insights
```

---

## 🗄️ Data Model

The analytical model follows a fact-and-dimension approach, subject to the final Warehouse implementation.

### Fact Table

- `fact_order` — stores order-level records, measures, and relevant dimension keys.

### Dimension Tables

- `dim_date` — supports date-based reporting.
- `dim_location` — supports geographical analysis.
- `dim_restaurant` — supports restaurant analysis, if implemented.
- `dim_dish` — supports dish-level analysis, if implemented.

The model is intended to support structured queries and reporting while reducing unnecessary duplication and improving analytical consistency.

---

## 💻 SQL Development

The SQL development component supports the reliability of the dashboard data.

- Schema and table queries in the `swiggy_project` schema.
- Record-count checks and data validation.
- Duplicate identification using `ROW_NUMBER()` and CTEs.
- Duplicate-management stored procedures.
- Date-value validation and conversion.
- Table-valued function for duplicate reporting, where implemented.
- Analytical queries for preparing data for reporting.

These activities help maintain data quality before the data is consumed by Power BI.

---

## 🖼️ Dashboard Preview

<img width="833" height="503" alt="image" src="https://github.com/user-attachments/assets/321f464f-f5cf-43c9-a660-ccfb896c2218" />


---

## 📁 Repository Structure

```text
swiggy-sales-analytics-fabric/
│
├── README.md
│
├── sql/
│   └── T-SQL-Swiggy.sql
│
├── warehouse/
│   └── Swiggy_DW/
│
├── pipelines/
│   └── LH-to-WH/
│
├── powerbi/
│   └── Swiggy-Analysis.pbix
│
└── screenshots/
    ├── dashboard-overview.png
    ├── sales-analysis.png
    └── location-analysis.png
```

*This is a suggested folder structure. Keep only files and folders that you actually upload to GitHub.*

---

## 🚀 How to Explore the Project

1. Clone or download the GitHub repository.
2. Review the SQL scripts to understand data cleaning and validation.
3. Explore the available Warehouse and pipeline artifacts.
4. Open `Swiggy-Analysis.pbix` using Power BI Desktop.
5. Review the dashboard KPIs, visualizations, and filters.
6. Configure your own data connections and permissions if reproducing the project.
7. Connect to the appropriate Microsoft Fabric resources if you want to refresh the data.

### Prerequisites

- Microsoft Fabric workspace with appropriate permissions.
- Power BI Desktop.
- Access to the source data and required Fabric resources.
- Compatible SQL environment for reviewing scripts.

---

## 🧠 Skills Demonstrated

- Microsoft Fabric Lakehouse and Warehouse
- ETL Pipeline Development
- SQL and T-SQL
- Data Cleaning and Data Quality
- Duplicate Detection and Management
- Fact and Dimension Modeling
- Power BI Dashboard Development
- DAX and Power Query
- KPI Design and Business Reporting
- Data Visualization and Analytical Thinking

---

## 👩‍💻 Author

### Riya Thokal

🚀 Aspiring Data Engineer | Microsoft Fabric | SQL | Power BI | Python

- 🐙 **GitHub:** [riyathokalofficial-stack](https://github.com/riyathokalofficial-stack)
- 💼 **LinkedIn:** [riya-engineer](https://www.linkedin.com/in/riya-engineer/)

---

⭐ If you find this project useful, consider giving the repository a star!

💬 Feedback and suggestions are always welcome.

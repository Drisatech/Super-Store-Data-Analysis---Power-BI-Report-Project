# 📊 Super Store Data Analysis – Power BI Report

### Full End-to-End Data Modeling, Analysis, and Visualization

This project delivers a complete Power BI data analysis solution using the Super Store Normalized dataset.
It covers data ingestion, cleaning, data modeling, DAX measure creation, visual analytics, drill-through pages, bookmarks, interactions, and publishing—built following professional BI development standards.

---

## ✅ Project Overview

This project analyzes sales, customer behavior, product performance, geographical insights, and profitability for a retail “Super Store.”

The final output is a fully interactive multi-page Power BI report (PBIX) with:

Sales & performance KPIs

Customer segmentation & lifetime insights

Regional/state analytics

Product & category performance

Profitability analysis (discount impact, loss-making orders)

Drill-through detail pages

Navigation, slicer sync, bookmarks & export configuration

---

### ✅ Dataset

The dataset (Super Store Normalized.xlsx) contains the following normalized tables:

Orders

Customers

Products

Locations

States

Products Pricing Tiers

Each sheet loads as a separate dimension or fact table in the Power BI model.

---

## 🏗️ 1. Data Loading & Preparation

### ✅ Importing Data

Power BI Desktop → Get Data → Excel → Load all sheets

Tables: Orders, Customers, Products, Locations, States, Pricing Tiers


### ✅ Power Query Transformations

Ensure Order Date is Date type

Rename inconsistent columns

Merge Locations with States (if needed)

Close & Apply changes

---

## 🧩 2. Data Modeling

The model follows a Star Schema:

Fact Table → Orders

Dimension Tables → Customers, Products, States, Locations


### ✅ Relationships

Orders ↔ Customers (Customer ID → Customer Id)

Orders ↔ Products (Product ID)

Locations ↔ States (State ID)

Locations ↔ Customers (if Customer ID is present)


All relationships use One-to-Many with Single-direction filtering.

---

## 🧮 3. DAX Measures

Core measures used across all report pages include:

Total Sales = SUM( Orders[Sales] )
Total Profit = SUM( Orders[Profit] )
Order Count = DISTINCTCOUNT( Orders[Order ID] )
Average Discount = AVERAGE( Orders[Discount] )
Customer Count = DISTINCTCOUNT( Customers[Customer Id] )
Profit Margin = DIVIDE( [Total Profit], [Total Sales], 0 )
Average Sales per Order = DIVIDE( [Total Sales], [Order Count], 0 )
Average Profit per Order = DIVIDE( [Total Profit], [Order Count], 0 )
%Orders with Discount =
    DIVIDE( CALCULATE( COUNTROWS( Orders ), Orders[Discount] > 0 ),
            COUNTROWS( Orders ), 0 )

Sales MTD = TOTALMTD( [Total Sales], Orders[Order Date] )
Sales YTD = TOTALYTD( [Total Sales], Orders[Order Date] )
Profit YTD = TOTALYTD( [Total Profit], Orders[Order Date] )

Additional measures were created for advanced filtering, profitability, and trend calculations.

---

## 📄 4. Report Pages & Visual Design

The report includes five (5) main report pages:

---

### ✅ Page 1 — Sales & Performance Overview

KPI cards: Total Sales, Total Profit, Order Count, Avg Discount

Monthly Sales & Profit trend (line chart)

Profit Margin KPI

Date/Region/Segment slicers

Cross-filter interactions configured

---

### ✅ Page 2 — Customer Insights

Top 10 customers by sales

Customer segment distribution (donut chart)

Detailed customer table

New customer metrics (First Order Date logic)

Trend of new vs returning customers

---

### ✅ Page 3 — Regional & State Insights

Filled/Shape map: Sales by State

Bar chart: Sales by State or Region

Matrix: Region → State breakdown

Region slicer synced across pages

---

### ✅ Page 4 — Product & Category Performance

Sales by Category (bar chart)

Top N Products (Top 10)

Matrix with drill-down: Category → Subcategory → Product

Treemap: Sales by Category with profit coloring

Conditional formatting on profitability metrics

---

### ✅ Page 5 — Profitability Analysis

Scatter Plot: Discount vs Profit

Orders with highest losses (table)

Profit trend (line chart)

Slicers: Category, Region, Segment

---

## 🔍 5. Interactions, Drill-through, Bookmarks & Navigation

### ✅ Cross-filtering

Format → Edit Interactions

Configure filter / highlight mode between visuals


### ✅ Drill-through (Customer Detail Page)

New “Customer Detail” page created

Drag Customer Name into Drill-through field well

Right-click any customer → Drill-through


### ✅ Bookmarks

View → Bookmarks Pane → Add bookmark

Use Selection Pane to show/hide visuals

Used for presentation or navigation panel


### ✅ Sync Slicers

View → Sync Slicers Pane

Sync Region, Category, Date slicers across multiple pages


### ✅ Export Options

File → Export → PDF

File → Publish → Power BI Service

---

## 🧪 6. Validation & Quality Checks

Before publishing, the following were verified:

Date table created & connected properly

All measures returning accurate values

No ambiguous relationships

Conditional formatting applied

Drill-through and bookmarks functional

Axis labels clear and readable

Page titles consistent

Visuals responsive under filtering

---

## 🚀 7. Publishing & Sharing

Published to Power BI Service via Home → Publish

Shared with stakeholders / exported as PDF

Power BI App or Publish-to-Web options (depending on tenant policy)

---

## 🗂️ 8. Files Included in This Repository

README.md (this file)

Super Store Normalized.xlsx (dataset)

.pbix Power BI Report file

Screenshot samples (optional folder)

---

## ✅ Project Outcome

This project demonstrates end-to-end business intelligence capabilities:

✅ Data Cleaning & Shaping
✅ Star Schema Data Modeling
✅ Professional DAX development
✅ Visual storytelling & analytics
✅ Customer, sales, geography & product insights
✅ Drill-throughs, bookmarks, slicers and navigation
✅ Publish-ready dashboard for stakeholders


---

## 📧 Contact

For questions or collaboration:

Name: Engr. Idris Aliyu

Role: Data Analyst / Engineer

Email: drisatech@gmail.com

GitHub: https://github.com/Drisatech

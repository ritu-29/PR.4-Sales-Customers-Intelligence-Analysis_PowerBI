# 📊 Sales & Customer Intelligence Dashboard (Power BI)

## 🚀 Project Overview

This project presents a **comprehensive Power BI dashboard** designed to analyze:

* 📈 Sales Performance
* 💰 Profit & Loss Trends
* 👥 Customer Behavior
* 🌍 Regional Insights

The solution is built using **data modeling best practices**, **advanced DAX**, and an **interactive multi-page dashboard**.

---

## 🎯 Objectives

* Build a **Star Schema Data Model**
* Implement **advanced DAX calculations**
* Apply **Time Intelligence (YTD, YoY, MoM)**
* Design **interactive dashboards**
* Enable **user-friendly navigation & filtering**

---

## 🧱 Data Model

### Tables Used:

* `Date_Dim`
* `Customer_Dim`
* `Product_Dim`
* `Region_Dim`
* `Sales_Fact`
* `Returns_Fact`

### Model Type:

✔ Star Schema
✔ One-to-Many Relationships
✔ Date table connected to Sales

---

## 🧮 Key DAX Measures

### 📊 Sales Metrics

```DAX
Total Sales = SUM(Sales_Fact[SalesAmount])

Total Profit = SUM(Sales_Fact[Profit])

Total Orders = DISTINCTCOUNT(Sales_Fact[OrderID])
```

---

### 📈 Time Intelligence

```DAX
Sales LY = 
CALCULATE([Total Sales], SAMEPERIODLASTYEAR(Date_Dim[Date]))

Sales YoY % = 
DIVIDE([Total Sales] - [Sales LY], [Sales LY])

Sales YTD = 
TOTALYTD([Total Sales], Date_Dim[Date])
```

---

### 📊 Advanced Measures

```DAX
Sales MoM % =
VAR PrevMonth =
    CALCULATE([Total Sales], PREVIOUSMONTH(Date_Dim[Date]))
RETURN
DIVIDE([Total Sales] - PrevMonth, PrevMonth, 0)
```

```DAX
Avg Sales per Customer =
AVERAGEX(
    VALUES(Customer_Dim[CustomerID]),
    [Total Sales]
)
```

---

## 📊 Dashboard Pages

---

# 🟢 1. Main Dashboard (Overview)

### 🎯 Purpose:

Quick snapshot for business decision-makers

### 📌 Visuals Used:

* KPI Cards:

  * Total Sales
  * Total Orders
  * Total Quantity
  * Total Customers
  * Total Profit

* 📈 Line Chart:

  * Sales & Profit Trend (Year-Month)

* 🍩 Donut Chart:

  * Sales by Category

* 📊 Bar Chart:

  * Sales by Region

* 📋 Matrix:

  * Category vs Region Sales

### 🎛 Features:

* Slicers (Category, Year, Region, Month)
* Dynamic filtering
* Clean UI design

---

# 🟡 2. Sales Analysis Page

### 🎯 Purpose:

Deep analysis of sales & product performance

### 📌 Visuals Used:

* 📊 Bar Chart:

  * Top Products by Sales

* 📈 Line Chart:

  * Monthly Sales Trend

* 🍩 Donut Chart:

  * Sales by Category

* 📋 Matrix:

  * Product-wise regional sales

* KPI Cards:

  * Sales YTD
  * Sales YoY %
  * Sales LY

### 🎛 Features:

* Top N filtering
* Interactive slicers
* Drill-down enabled

---

# 🔵 3. Customer Analysis Page

### 🎯 Purpose:

Understand customer behavior and profitability

### 📌 Visuals Used:

* 📊 Bar Chart:

  * Profit by Customer

* 📈 Line Chart:

  * Orders Trend

* 🍩 Donut Chart:

  * Sales by Segment

* 📋 Table:

  * Customer-wise Sales & Profit

* KPI Cards:

  * Total Customers
  * Avg Sales per Customer

### 🎛 Features:

* Customer segmentation
* Profitability analysis
* Dynamic filtering

---

## 🎨 UI & UX Design

* Dark Theme Dashboard (#1E1E1E)
* High contrast KPI cards
* Consistent color palette:

  * 🔵 Blue → Sales
  * 🟠 Orange → Profit
* Grid alignment & spacing
* Clean typography

---

## 🔄 Interactivity Features

* Slicers:

  * Year, Month, Region, Category

* Cross-filtering between visuals

* Drill Down / Drill Through

* Bookmark Navigation (for page switching)

---

## 📱 Mobile Optimization

* Simplified layout
* Focus on KPI cards
* Key charts prioritized

---

## 🔐 Security

* Row-Level Security (RLS)
* Region-based access control

---

## 📦 Deliverables

* ✔ Power BI File (.pbix)
* ✔ Interactive Dashboard
* ✔ DAX Documentation
* ✔ Mobile Layout
* ✔ Project Documentation

---

## 💡 Key Insights

* Sales show **seasonal trends**
* Certain regions contribute **higher revenue**
* Some customers are **high profit generators**
* Profit margin varies significantly across categories

---

## 📌 Conclusion

This project demonstrates how Power BI can transform raw data into **actionable insights** through:

✔ Data Modeling
✔ Advanced Analytics
✔ Interactive Visualization

---

## 🙌 Author

**Ritu Poonjani**
Aspiring Data Analyst | Power BI Developer

---

⭐ If you like this project, feel free to give a star!

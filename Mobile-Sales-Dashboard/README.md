# 📱 Mobile Sales Dashboard | Power BI Project

![Power BI](https://img.shields.io/badge/Tool-Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/Language-DAX-blue?style=for-the-badge)
![Power Query](https://img.shields.io/badge/ETL-Power%20Query-0078D4?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)

An **interactive Power BI dashboard** built to analyse mobile device sales performance across brands, cities, payment methods, and time periods — transforming raw transactional data into actionable business intelligence for sales teams and decision-makers.

---

## 📋 Table of Contents

- [About the Project](#about-the-project)
- [Dashboard Overview](#dashboard-overview)
- [Key Metrics](#key-metrics)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [DAX Measures Used](#dax-measures-used)
- [Data Cleaning & Transformation](#data-cleaning--transformation)
- [Business Insights](#business-insights)
- [Setup & Usage](#setup--usage)
- [Developer](#developer)

---

## 📌 About the Project

The **Mobile Sales Dashboard** is a business intelligence project built in Power BI to analyse sales data for mobile devices across multiple brands, Indian cities, and payment channels.

The dashboard was designed for sales teams, management, and decision-makers to quickly identify top-performing cities, brands, customer preferences, and seasonal trends — all from a single interactive report page.

This project was built as part of my **Data Analytics Internship at Oasis Infobyte** and my academic work at **Bhavan's College, Mumbai**.

---

## 🖥️ Dashboard Overview

The dashboard is structured into the following visual sections:

- **Top KPI Cards** — Total Sales, Total Quantity, Total Transactions, Average Order Value
- **City-Wise Map** — Geographic sales distribution across India
- **Brand Performance** — Side-by-side brand comparison (Apple, Samsung, Vivo, Xiaomi, OnePlus)
- **Monthly Sales Trend** — Line/bar chart showing sales over time with filters
- **Payment Method Breakdown** — UPI, Cash, Credit Card, Debit Card split
- **Mobile Model Analysis** — Model-wise quantity and revenue
- **Customer Ratings Distribution** — Rating spread across transactions
- **Dynamic Slicers** — Filter by Brand, Payment Method, Mobile Model, Month

---

## 📊 Key Metrics

| Metric | Value |
|--------|-------|
| Total Sales | ₹769 Million |
| Total Quantity Sold | 19,000+ Units |
| Total Transactions | 4,000+ |
| Average Order Value | ₹40,000 |
| Brands Covered | 5 (Apple, Samsung, Vivo, Xiaomi, OnePlus) |
| Cities Covered | Multiple Indian cities |
| Payment Methods | UPI, Cash, Credit Card, Debit Card |

---

## ✅ Features

### 1. 📦 KPI Summary Cards
- Total Sales (₹769M), Total Quantity (19K), Total Transactions (4K), Average Order Value (₹40K)
- Instant snapshot of overall business performance

---

### 2. 🗺️ City-Wise Sales Map
- Geographic visualisation of sales distribution across Indian cities
- Bubble size represents sales volume per city
- Identifies highest and lowest performing markets at a glance

---

### 3. 🏷️ Brand-Wise Comparison
- Side-by-side performance analysis for Apple, Samsung, Vivo, Xiaomi, and OnePlus
- Compares total revenue, quantity sold, and average price per brand
- Highlights market share distribution

---

### 4. 📅 Monthly & Day-Wise Sales Trend
- Line and bar charts showing revenue and quantity trends over time
- Filter by month to isolate seasonal performance
- Identifies peak selling months and slow periods

---

### 5. 💳 Payment Method Insights
- Breakdown of transactions by payment type: UPI, Cash, Credit Card, Debit Card
- Reveals customer payment preferences by brand and region

---

### 6. 📱 Mobile Model Analysis
- Model-level breakdown of quantity sold and revenue
- Identifies best-selling models across all brands

---

### 7. ⭐ Customer Ratings Distribution
- Histogram / bar chart of customer ratings across transactions
- Highlights product satisfaction patterns

---

### 8. 🔽 Dynamic Slicers
- Filter the entire dashboard by:
  - Brand (Apple / Samsung / Vivo / Xiaomi / OnePlus)
  - Payment Method
  - Mobile Model
  - Month
- All visuals update simultaneously when a slicer is applied

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| BI Tool | Microsoft Power BI Desktop |
| Data Transformation | Power Query (M Language) |
| Calculations | DAX (Data Analysis Expressions) |
| Visualisations | Bar, Line, Map, Pie, Slicer, Card, Table |
| Data Source | CSV / Excel |

---

## 📐 DAX Measures Used

```dax
-- Total Sales
Total Sales = SUM(Sales[Total Price])

-- Total Quantity
Total Quantity = SUM(Sales[Quantity])

-- Total Transactions
Total Transactions = COUNTROWS(Sales)

-- Average Order Value
Avg Order Value = DIVIDE([Total Sales], [Total Transactions], 0)

-- Month-over-Month Growth
MoM Growth % =
VAR CurrentMonthSales = [Total Sales]
VAR PrevMonthSales = CALCULATE([Total Sales], DATEADD('Date'[Date], -1, MONTH))
RETURN DIVIDE(CurrentMonthSales - PrevMonthSales, PrevMonthSales, 0)
```

---

## 🔧 Data Cleaning & Transformation

All data cleaning was performed in **Power Query** before loading into the data model:

- Removed duplicate rows and blank entries
- Standardised column data types (date, currency, text)
- Created a separate `Date` table for time intelligence functions
- Extracted Month Name, Month Number, and Year from transaction dates
- Trimmed and formatted brand/model name columns for consistency
- Created calculated columns for price bands and rating categories

---

## 💡 Business Insights

Key findings from the dashboard analysis:

- **Top Cities** — Certain metro cities contribute disproportionately to total revenue
- **Brand Dominance** — Apple and Samsung lead in revenue; Xiaomi and Vivo lead in volume
- **Payment Trends** — UPI is the most commonly used payment method across all brands
- **Seasonality** — Clear monthly peaks visible — ideal for inventory planning
- **Model Performance** — A small number of models account for the majority of sales (80/20 pattern)
- **Customer Ratings** — Most transactions are rated 4 or above, indicating high satisfaction

---

## ⚙️ Setup & Usage

### Prerequisites
- Microsoft Power BI Desktop installed ([Download here](https://powerbi.microsoft.com/desktop/))

### Steps

**1. Clone the repository**
```bash
git clone https://github.com/soham-88/Data-analytics-dashboards.git
```

**2. Navigate to the project folder**
```
cd Data-analytics-dashboards/Mobile-Sales-Dashboard
```

**3. Open the dashboard**
- Open Power BI Desktop
- Click **File → Open**
- Select the `.pbix` file from the folder

**4. Explore the dashboard**
- Use the slicers on the left/top panel to filter by Brand, Month, Payment Method, or Model
- Hover over any visual for detailed tooltips
- Click any bar/segment to cross-filter all visuals on the page

---

## 👨‍💻 Developer

**Soham Gopal Pawar**  
B.Sc. Computer Science (SYCS) — Bhavan's College, Mumbai  
Data Analytics Intern — Oasis Infobyte

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?style=for-the-badge&logo=linkedin)](https://www.linkedin.com/in/soham-pawar-984b32319/)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-black?style=for-the-badge&logo=github)](https://github.com/soham-88)

---

> ⭐ If you found this project useful, consider giving the repository a star!

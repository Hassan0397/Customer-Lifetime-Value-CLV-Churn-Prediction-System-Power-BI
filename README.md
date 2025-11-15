# 📊 Customer Lifetime Value (CLV) & Churn Prediction System — Power BI

A **Power BI** project that predicts customer churn, calculates Customer Lifetime Value (CLV), estimates revenue at risk, and provides actionable insights using financial, behavioral, and satisfaction data.

---

## 🚨 Problem Statement

Companies, especially subscription-based and service-based, often face **significant revenue loss** due to unpredictable customer churn.

- High-value customers may churn without warning  
- Customer Success teams lack prioritization tools for retention  
- Finance teams cannot forecast revenue at risk effectively  
- Data is scattered across CRM, support, and survey systems  

**This project addresses these challenges by centralizing customer insights into an interactive Power BI dashboard.**

---

## ✅ Solution

This system provides a **centralized analytics platform** that:

- Calculates **Customer Lifetime Value (CLV)**  
- Predicts **Churn Probability (%)**  
- Estimates **Revenue at Risk**  
- Highlights high-value and at-risk customers  
- Integrates **CRM, purchase, support, and feedback data**  
- Offers **Executive dashboards, Drillthrough pages, and Tooltips** for detailed insights  

The dashboard enables **Executives, Finance, Customer Success, Marketing, and Sales** teams to make informed decisions and prioritize retention strategies.

---

## 🚀 Project Workflow

### 🟦 1. Data Preparation
Created realistic CSV datasets:

- `dim_Customers.csv` → Customer profile data (ID, Name, Segment, Region, Subscription Plan, Acquisition Channel)  
- `dim_Date.csv` → Calendar table for time intelligence  
- `fact_Purchases.csv` → Purchase history (Amount, Category, Date)  
- `fact_SupportTickets.csv` → Support tickets (Severity, Status, Resolution Time, CSAT)  
- `fact_Feedback.csv` → Customer feedback (NPS, Comments)  

**Cleaning Steps:**

- Standardized text casing for names, segments, and categories  
- Removed duplicate Customer IDs  
- Filled missing NPS/CSAT values  
- Converted numeric columns to Currency/Decimal  

---

### 🟩 2. Data Load
Imported all CSVs into **Power BI Desktop** and verified:

- IDs → **Whole Number**  
- Amounts → **Currency**  
- Dates → **Date**  
- Flags/Statuses → **Text/Boolean**  

---

### 🟨 3. Data Modeling
Built a **Star Schema**:

- **Dimension Tables:** `dim_Customers`, `dim_Date`  
- **Fact Tables:** `fact_Purchases`, `fact_SupportTickets`, `fact_Feedback`  
- **Relationships:**  
  - `dim_Customers[CustomerID]` → All fact tables  
  - `dim_Date[Date]` → All fact tables  
- Marked `dim_Date[Date]` as the **official Date Table**  

---

### 🟧 4. Transformations (Power Query)
- Renamed columns for clarity  
- Standardized text fields (Region, Segment, Plan)  
- Converted date and currency fields  
- Removed duplicates in dimension tables  
- Replaced nulls with default values or “Not Provided”  
- Added calculated columns for flags (high-risk tickets, churn indicators)  

---

### 🟧 5. Executive Dashboard

## Page 1 — [Executive Overview](https://github.com/Hassan0397/Customer-Lifetime-Value-CLV-Churn-Prediction-System-Power-BI/blob/main/CLV%20%24%20Churn%20Risk%20Overview.png) 
- **KPI Cards:** Total Revenue, Avg CLV, Avg Churn %, Revenue at Risk  
- **Line Charts:** Purchases & NPS trends  
- **Map:** Customer distribution by region  

---

## Page 2 — [Customer Risk & Detail](https://github.com/Hassan0397/Customer-Lifetime-Value-CLV-Churn-Prediction-System-Power-BI/blob/main/Customer%20Details.png)
- Customer-level table with CLV, Churn %, Revenue at Risk, Loyalty Score, Days Since Last Purchase  
- Conditional formatting for high-risk customers  

---

## Page 3 — [Drillthrough: Customer Profile](https://github.com/Hassan0397/Customer-Lifetime-Value-CLV-Churn-Prediction-System-Power-BI/blob/main/Customer%20Profile.png)
- Line chart: Purchase history  
- Table: Support ticket history  
- Table: NPS & feedback comments  

---

## Page 4 — Tooltip: Quick Customer Summary
- Avg NPS, recent tickets, last purchase, revenue at risk  

---

## Key Outcomes
- **Executives:** Visibility into churn & revenue at risk  
- **Customer Success:** Prioritized retention list  
- **Finance:** CLV-based revenue forecasting  
- **Sales/Marketing:** Targeted upsell/renewal campaigns  
- **Product Teams:** Insights into customer pain points

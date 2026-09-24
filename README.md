# 💊 Pharmaceutical Sales & Commercial Analytics — SQL + Power BI

An end-to-end commercial analytics project analyzing pharmaceutical sales, prescriptions, products, doctors, territories, and distributors to support data-driven decisions for sales and commercial teams.

---

## 📖 Project Overview

This project simulates a real-world pharmaceutical commercial analytics environment. It combines **SQL** for data validation and analysis with **Power BI** for interactive dashboard reporting, covering the full journey from raw relational data to business-ready insights.

The analysis spans eight interconnected areas of the pharma commercial business: customers, doctors, products, sales transactions, prescriptions, distributors, territories, and time. Together, these datasets make it possible to evaluate revenue, profitability, prescription behavior, and sales-force performance from multiple angles.

The project is built to reflect how a Data Analyst working in a pharmaceutical company might approach commercial reporting — starting with clean, validated data and ending with dashboards that support real business questions.

---

## ❓ Problem Statement

Pharmaceutical companies operate across many products, therapy areas, territories, and prescribing doctors, which makes it difficult to get a clear, consolidated view of commercial performance. Without a structured analytics layer, it's hard to answer basic but important questions:

- Which products and therapy areas are actually driving revenue and profit?
- Are prescription trends translating into sales?
- Which territories are hitting their targets, and which ones need attention?
- Which distributors are performing well, and which are underdelivering?

This project addresses that gap by building a structured SQL + Power BI solution that consolidates commercial data into clear, actionable dashboards.

---

## 🎯 Business Objectives

Develop an end-to-end Pharmaceutical Sales & Commercial Analytics solution to analyze:

- Sales performance
- Revenue and profitability
- Product performance
- Therapy-area performance
- Prescription trends
- Doctor engagement
- Territory performance
- Distributor performance
- Regional sales
- Target achievement
- Sales growth
- Underperforming territories and sales opportunities

The goal is to help pharmaceutical management identify growth opportunities, improve product and territory performance, optimize sales-force allocation, and support data-driven commercial decisions.

---

## 🔄 Project Workflow

1. **Data Collection** — Organized eight relational tables covering customers, doctors, products, sales, prescriptions, distributors, territories, and dates.
2. **Data Validation (SQL)** — Checked record counts, duplicates, NULLs, and referential integrity across tables.
3. **Data Analysis (SQL)** — Queried sales, product, prescription, and territory data to surface performance patterns.
4. **Data Modeling (Power BI)** — Built a relational data model connecting all tables through common keys.
5. **DAX Measures** — Created KPI and analytical measures for revenue, profit, prescriptions, and target achievement.
6. **Dashboard Development** — Designed four dashboards covering executive, product, doctor, and territory/distributor views.
7. **Insight Generation** — Interpreted the visuals to produce clear, business-relevant takeaways.

---

## 🗃️ Dataset & Data Model

The project uses **8 relational tables**, connected through primary and foreign keys to form a star-schema-style model centered on the Sales and Prescriptions tables.

### 1. Customers
| Column | Description |
|---|---|
| Customer_ID | Unique customer identifier |
| Customer_Name | Customer name |
| Gender | Customer gender |
| Age | Customer age |
| City | Customer city |
| State | Customer state |
| Customer_Segment | Customer segment classification |

### 2. Doctors
| Column | Description |
|---|---|
| Doctor_ID | Unique doctor identifier |
| Doctor_Name | Doctor name |
| Specialty | Medical specialty |
| City | Doctor's city |
| State | Doctor's state |
| Experience_Years | Years of experience |
| Doctor_Type | Type/category of doctor |

### 3. Products
| Column | Description |
|---|---|
| Product_ID | Unique product identifier |
| Product_Name | Product name |
| Therapy_Area | Therapy area (e.g., Diabetes, Cardiology) |
| Product_Category | Category (Tablet, Capsule, Injection, etc.) |
| Brand | Brand name |
| Unit_Cost | Cost per unit |
| Unit_Price | Selling price per unit |
| Launch_Date | Product launch date |
| Product_Status | Active/discontinued status |

### 4. Sales
| Column | Description |
|---|---|
| Sale_ID | Unique sale identifier |
| Date_ID | Foreign key to Date table |
| Product_ID | Foreign key to Products table |
| Doctor_ID | Foreign key to Doctors table |
| Distributor_ID | Foreign key to Distributors table |
| Territory_ID | Foreign key to Territories table |
| Units_Sold | Number of units sold |
| Unit_Price | Price per unit |
| Discount | Discount applied |
| Revenue | Calculated revenue |
| Cost | Calculated cost |
| Profit | Calculated profit |

### 5. Prescriptions
| Column | Description |
|---|---|
| Prescription_ID | Unique prescription identifier |
| Date_ID | Foreign key to Date table |
| Doctor_ID | Foreign key to Doctors table |
| Product_ID | Foreign key to Products table |
| Customer_ID | Foreign key to Customers table |
| Prescription_Type | Type of prescription |
| Quantity_Prescribed | Quantity prescribed |

### 6. Distributors
| Column | Description |
|---|---|
| Distributor_ID | Unique distributor identifier |
| Distributor_Name | Distributor name |
| City | Distributor city |
| State | Distributor state |
| Region | Distributor region |
| Distributor_Type | Type of distributor |

### 7. Territories
| Column | Description |
|---|---|
| Territory_ID | Unique territory identifier |
| Territory_Name | Territory name |
| Region | Region the territory belongs to |
| State | State |
| Sales_Rep_ID | Assigned sales representative |
| Target_Sales | Sales target for the territory |

### 8. Date
| Column | Description |
|---|---|
| Date_ID | Unique date identifier |
| Date | Calendar date |
| Year | Year |
| Quarter | Quarter |
| Month_Number | Month number |
| Month_Name | Month name |
| Year_Month | Year-month combination |

---

## 🧹 Data Cleaning & Preparation

Before analysis, the raw data was validated and prepared to ensure consistency across all eight tables:

- Verified record counts across all tables to confirm completeness.
- Checked for duplicate records in key identifier columns.
- Identified and reviewed NULL values in critical fields.
- Validated primary and foreign key relationships between related tables.
- Checked for orphan records (e.g., sales entries referencing non-existent products or territories).
- Standardized date fields to support consistent time-based analysis.

This step ensured that downstream SQL analysis and the Power BI data model were built on reliable, consistent data.

---

## ⚙️ Feature Engineering / Data Modeling

A relational data model was built in Power BI connecting all eight tables through their respective keys (Product_ID, Doctor_ID, Territory_ID, Distributor_ID, Customer_ID, and Date_ID), with the Sales and Prescriptions tables acting as the central fact tables.

Key calculated fields used throughout the project:

| Metric | Formula |
|---|---|
| Revenue | Units_Sold × Unit_Price − Discount |
| Cost | Units_Sold × Unit_Cost |
| Profit | Revenue − Cost |
| Profit Margin % | Profit ÷ Revenue |
| Target Achievement % | Revenue ÷ Target_Sales |
| Sales Growth % | Current Period Revenue vs. Previous Period Revenue |

These calculations form the foundation for all KPIs and visuals across the four dashboards.

---

## 🧮 SQL Analysis

SQL was used to validate the dataset and perform the core analytical work that informed the Power BI dashboards.

### Data Validation
- Record counts across all tables
- Duplicate checks on key identifier columns
- NULL value checks on critical fields
- Primary/foreign key validation
- Orphan record checks (e.g., sales linked to missing products or territories)

### Sales Analysis
- Total revenue and total profit
- Units sold
- Monthly sales trends
- Regional sales breakdown
- Product-level sales
- Therapy-area sales

### Product Analysis
- Top-performing products
- Bottom-performing products
- Product profitability
- Product category performance
- Therapy-area performance

### Prescription Analysis
- Prescription volume
- Doctor-level performance
- Specialty-level performance
- Product prescription trends
- Prescription-to-sales relationships

### Territory & Distributor Analysis
- Territory-level revenue
- Target achievement by territory
- Distributor performance
- Regional performance comparison
- Identification of underperforming territories

---

## 📊 Business KPIs

The following KPIs were developed as DAX measures in Power BI and used consistently across dashboards:

- Total Revenue
- Total Profit
- Profit Margin %
- Units Sold
- Total Prescriptions
- Sales Growth %
- Target Achievement %
- Active Doctors
- Total Quantity Prescribed
- Top Doctor Revenue
- Top Doctor Prescription Volume
- Average Revenue per Distributor

---

## 📈 Power BI Dashboard Overview

Power BI was used to build the full reporting layer of this project, including:

- Data modeling and relationship management
- KPI development using DAX
- Interactive, filterable dashboards
- Slicers for dynamic exploration (by region, therapy area, time period, etc.)
- Trend analysis across months and quarters
- Product and territory comparisons
- Business-user-friendly interactive exploration

Four dashboards were built, each focused on a specific area of the commercial business.

### 🧭 Dashboard 1 — Executive Commercial Overview

**Purpose:** Provide a high-level view of pharmaceutical commercial performance, revenue, profitability, sales growth, prescriptions, and target achievement.

**KPI Cards**

| KPI | Value |
|---|---|
| Total Revenue | 979.91M |
| Total Profit | 441.84M |
| Profit Margin | 45.09% |
| Units Sold | 9M |
| Prescription Volume | 20K |
| Sales Growth | 16.48% |
| Target Achievement Rate | 21.46% |

**Main Visuals**
1. Monthly Revenue & Profit Trend
2. Revenue vs Target
3. Revenue by Therapy Area
4. Top 10 Products by Revenue
5. Sales & Profit by Region
6. Revenue Contribution by Product Category

**Key Insights**
- Monthly revenue stays relatively steady, ranging between approximately **77M and 87M**.
- May and December show notable revenue peaks above **85M**.
- Diabetes is the leading therapy area, generating approximately **156M** in revenue.
- Respiratory follows with approximately **129M**.
- Cardiology and Gastroenterology each generate approximately **126M**.
- Metforol 5mg is the highest individual revenue-generating product at approximately **90M**.
- South is the highest-revenue region, with approximately **333M** in revenue and **152M** in profit.
- Tablets dominate the portfolio with approximately **608.8M** in revenue — more than 62% of total revenue.
- Capsules contribute approximately **169.81M**.
- Injections contribute approximately **114.05M**.

---

### 💊 Dashboard 2 — Product & Therapy Performance

**Purpose:** Analyze product-level revenue, profitability, pricing, volume, and therapy-area performance.

**KPI Cards**

| KPI | Value |
|---|---|
| Total Products | 50 |
| Total Revenue | 979.91M |
| Total Profit | 441.84M |
| Profit Margin | 45.09% |
| Units Sold | 9M |
| Prescription Volume | 20K |

**Main Visuals**
1. Revenue & Profit by Product
2. Top 10 Products by Revenue
3. Bottom 10 Products by Revenue
4. Product Profitability Matrix / Analysis
5. Revenue by Therapy Area
6. Prescription Volume by Therapy Area
7. Monthly Product Sales Trend
8. Price vs Units Sold Scatter Plot

**Key Insights**
- Metforol 5mg generates approximately **90M** in revenue, the highest of any product.
- Bronchial 25mg follows with approximately **76M** in revenue.
- Heartrin 5mg is among the lowest revenue-generating products, at approximately **2.4M**.
- Algofen 20mg generates approximately **2.5M**.
- Metforol 5mg also produces the highest absolute profit, at approximately **48M**.
- Bronchial 25mg follows with approximately **39M** in profit.
- The price-vs-volume analysis shows many high-volume products clustered around lower price points — an observed pattern in the data rather than a formal price elasticity calculation.

---

### 🩺 Dashboard 3 — Doctor & Prescription Analytics

**Purpose:** Analyze physician engagement, prescription behavior, specialty performance, and the relationship between prescriptions and pharmaceutical sales.

**KPI Cards**
- Active Doctors: **300**
- Total Prescriptions: **20K**
- Average Prescriptions per Doctor: **39.22**
- Revenue from Prescribed Products
- Top Doctor Revenue
- Top Doctor Prescription Volume

**Main Visuals**
1. Top 10 Doctors by Prescription Volume
2. Top 10 Doctors by Revenue
3. Prescriptions by Specialty
4. Revenue by Specialty
5. Doctor Prescription → Sales Analysis
6. Monthly Prescription Trend
7. Product Preference by Specialty Matrix

**Key Insights**
- There are **300 active doctors** represented in the prescription data.
- Total prescription volume is approximately **20K**.
- Average prescriptions per doctor is approximately **39.22**.
- Dr. Deepa Mishra has the highest prescription count, at **204 prescriptions**.
- Dr. Varun Bose follows with **185 prescriptions**.
- General Physicians generate the highest specialty-level revenue, at approximately **145.63M**.
- Endocrinologists generate approximately **134.89M**.
- Pulmonologists generate approximately **109.48M**.
- General Physicians and Cardiologists each account for more than **3K prescriptions**.

---

### 🗺️ Dashboard 4 — Territory, Distributor & Sales Force Performance

**Purpose:** Analyze regional sales, territory performance, distributor contribution, target achievement, and sales opportunities.

**KPI Cards**

| KPI | Value |
|---|---|
| Total Territories | 30 |
| Total Distributors | 100 |
| Total Revenue | 979.91M |
| Target Achievement | 21.46% |
| Profit Margin | 45.09% |
| Average Revenue per Distributor | 9.80M |

**Main Visuals**
1. Revenue by Territory / Region
2. Actual Sales vs Target
3. Territory Performance Matrix
4. Top 10 Territories
5. Bottom 10 Territories
6. Distributor Revenue Ranking
7. Distributor Performance by Region
8. Monthly Regional Sales Trend
9. Sales Opportunity / Underperforming Territory Analysis (scatter chart)

**Scatter Chart Logic**

| Axis / Attribute | Field |
|---|---|
| X-axis | Total Revenue |
| Y-axis | Target Achievement % |
| Legend | Territory Name |
| Size | Total Profit |

**Interpretation Framework**
- High revenue + high target achievement → strong territory performance
- High revenue + lower target achievement → potential sales opportunity
- Low revenue + low target achievement → underperforming territory
- Low revenue + high target achievement → smaller but relatively efficient territory

**Key Insights**
- South is the highest-revenue region, at approximately **332.82M**.
- North follows with approximately **222.03M**.
- West generates approximately **219.01M**.
- Coimbatore Territory leads all territories in sales, at approximately **73M**.
- New Delhi Territory follows at approximately **71M**.
- Nagpur Territory generates approximately **40M**.
- TrustMed-New Delhi and HealthDistrib-Mumbai are among the leading distributors, generating approximately **20M–29M** in annual sales.
- Bhopal and Nagpur are examples of territories identified through the scatter analysis as having relatively high targets but lower realization, marking them as areas for closer monitoring.

---

## 💡 Key Insights

- Diabetes and Respiratory are the strongest therapy areas by revenue, while Cardiology and Gastroenterology are close behind.
- Tablets are the dominant product category, contributing more than 62% of total revenue.
- A small group of products (led by Metforol 5mg) accounts for a disproportionate share of both revenue and profit.
- Prescription activity is concentrated among a subset of high-volume doctors, with General Physicians and Cardiologists prescribing most frequently.
- South is consistently the top-performing region across both revenue and profit.
- Target achievement (21.46% overall) is low relative to revenue generated, suggesting sales targets may be set aggressively or that territory-level execution varies significantly.
- Certain territories, such as Bhopal and Nagpur, show a gap between assigned targets and actual realization, making them candidates for further review.

---

## 🚀 Business Value

This project is designed to support the kind of decisions a pharmaceutical commercial team regularly faces:

- **Commercial performance monitoring** — track revenue, profit, and growth over time.
- **Product portfolio analysis** — identify which products and therapy areas are performing well or underperforming.
- **Territory planning** — compare territory-level performance against targets.
- **Sales-force allocation** — surface which territories may need more support or a revised strategy.
- **Distributor evaluation** — compare distributor contribution across regions.
- **Prescription trend analysis** — connect doctor prescribing behavior with actual sales outcomes.
- **Revenue and profitability monitoring** — maintain visibility into margins across products and regions.
- **Target tracking** — monitor how actual sales compare to territory targets.
- **Identification of sales opportunities** — flag high-revenue territories that are still under target.

As a portfolio project, this solution demonstrates the analytical workflow and reporting structure that would support these decisions in a real commercial environment, using a simulated dataset.

---

## ❔ Business Questions Answered

1. What is the total pharmaceutical revenue and profit?
2. Which therapy areas generate the most revenue?
3. Which products are the strongest revenue and profit contributors?
4. Which products have low sales performance?
5. How are prescription volumes changing over time?
6. Which doctors generate the highest prescription volumes?
7. Which specialties contribute the most revenue?
8. Which regions generate the highest sales?
9. Which territories are meeting or missing their targets?
10. Which distributors contribute the most revenue?
11. Where are the potential sales opportunities?
12. Which territories require closer performance monitoring?

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| SQL / MySQL | Data querying, validation and analysis |
| Power BI | Interactive dashboard development |
| DAX | KPI and analytical measure development |
| Excel / CSV | Data preparation and source data |

---

## 📁 Project Structure

```
pharmaceutical-sales-commercial-analytics/
│
├── Data/
│   ├── Customers.csv
│   ├── Doctors.csv
│   ├── Products.csv
│   ├── Sales.csv
│   ├── Prescriptions.csv
│   ├── Distributors.csv
│   ├── Territories.csv
│   └── Date.csv
│
├── SQL/
│   └── pharmaceutical-sales-analysis.sql
│
├── PowerBI/
│   └── pharmaceutical-sales-commercial-analytics.pbix
│
├── Screenshots/
│   ├── executive-commercial-overview.png
│   ├── product-therapy-performance.png
│   ├── doctor-prescription-analytics.png
│   └── territory-distributor-sales-force.png
│
└── README.md
```

> Note: File and folder names above are placeholders reflecting the intended structure. Update them to match your actual repository files if they differ.

---

## 🖼️ Dashboard Preview

### Executive Commercial Overview
![Executive Commercial Overview](Screenshots/executive-commercial-overview.png)

### Product & Therapy Performance
![Product & Therapy Performance](Screenshots/product-therapy-performance.png)

### Doctor & Prescription Analytics
![Doctor & Prescription Analytics](Screenshots/doctor-prescription-analytics.png)

### Territory, Distributor & Sales Force Performance
![Territory, Distributor & Sales Force Performance](Screenshots/territory-distributor-sales-force.png)

---

## 📌 GitHub Image Path Setup

To ensure dashboard screenshots render correctly on GitHub:

1. Create a folder named `Screenshots/` in the root of the repository.
2. Add the four dashboard screenshots using the exact filenames listed above.
3. Keep the relative paths (`Screenshots/filename.png`) as used in this README — do not use absolute local file paths.
4. Confirm the images render correctly by previewing the README on GitHub before finalizing.

---

## 🤝 Connect With Me

If you have feedback on this project or would like to discuss it, feel free to reach out.

- **LinkedIn:** [Add your LinkedIn URL here]
- **Email:** [Add your email here]
- **Portfolio:** [Add your portfolio URL here]

---

⭐ If you found this project useful or interesting, consider giving the repository a star.

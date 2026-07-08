# alif-FMCG-Product-Analytics-Dashboard
A multi-page Power BI dashboard analyzing sales performance, marketing funnel, and customer behavior for the gum product category on Alif marketplace across 7 regions of Uzbekistan.


## 📌 Project Overview
This Power BI dashboard provides a comprehensive 
analysis of the gum product category on Alif — 
one of Uzbekistan's leading fintech and marketplace 
platforms. The dashboard covers sales performance, 
marketing funnel efficiency, and customer behavior 
across 7 regions of Uzbekistan.

---

## 📊 Dashboard Pages

### Page 1 — Sales & Financial Overview
- Total Sales, Contribution Margin, Avg LTV, Avg CAC, LTV/CAC Ratio
- Contribution Margin by Brand
- Unit Price vs Cost by Product
- Commission Amount by Channel Type and Channel Name
- Monthly CAC Trend with Total Reach

### Page 2 — Marketing & Funnel Performance
- Marketing Funnel: Reach → Conversions → Trials → Trusted → Revenue per Conversion
- Total Marketing Expenses, Funnel Efficiency %, Trial Rate %, Trust Rate %
- Funnel Efficiency by Regions
- Product Availability (Shelf Share % and Fill Rate %)
- Total Revenue by Month

### Page 3 — Customer Analytics
- Total Customers, Loyal Customers, New Customers, Lost Customers
- Customer Segmentation Overview (Pie Chart)
- Customer Dynamics by Regions
- Churn Rate % and Repeat Rate % (Gauge)
- Customer Retention vs. Churn Dynamics (Monthly Trend)

---

## 🗂️ Data Model
The data model consists of 8 tables:

**Dimension Tables:**
- dim_date — Date hierarchy (year, quarter, month, week)
- dim_product — Product details (brand, category, price, cost)
- dim_region — Region details (city, district, population)
- dim_channel — Sales channel (type, name, commission %)

**Fact Tables:**
- fact_sales — Sales transactions
- fact_marketing — Marketing campaigns and funnel metrics
- fact_customer — Customer behavior and segmentation
- fact_supply — Supply chain and distribution metrics
- fact_funnel — Funnel performance by region
- fact_unit_economics — LTV, CAC, ROI, break-even metrics
- fact_diagnostics — Business health flags by region

---

## 📐 Key DAX Measures

### Sales
- Total Sales = SUM(fact_sales[sotuv_summa])
- Total Profit = SUM(fact_sales[foyda_summa])
- Profit Margin % = DIVIDE([Total Profit], [Total Sales], 0)

### Marketing
- Total Marketing Expenses = SUM(fact_marketing[marketing_xarajat])
- Conversion Rate % = DIVIDE(SUM(fact_marketing[conversion_soni]), SUM(fact_marketing[reach_soni]), 0)
- Trial Rate % = DIVIDE(SUM(fact_marketing[trial_soni]), SUM(fact_marketing[reach_soni]), 0)
- Trust Rate % = DIVIDE(SUM(fact_marketing[trust_soni]), SUM(fact_marketing[trial_soni]), 0)
- ROI % = DIVIDE([Total Profit] - [Total Marketing Expenses], [Total Marketing Expenses], 0)

### Customer
- Total Customers = SUM(fact_customer[jami_aktiv_mijoz])
- New Customers = SUM(fact_customer[yangi_mijoz])
- Loyal Customers = SUM(fact_customer[qayta_xarid_mijoz])
- Lost Customers = SUM(fact_customer[churn_mijoz])
- Churn Rate % = DIVIDE([Lost Customers], [Total Customers], 0)

### Unit Economics
- Avg LTV = AVERAGE(fact_customer[ltv_uzs])
- Avg CAC = DIVIDE([Total Marketing Expenses], SUM(fact_marketing[conversion_soni]), 0)
- LTV CAC Ratio = DIVIDE([Avg LTV], [Avg CAC], 0)

---

## 🛠️ Tools Used
- **Power BI Desktop** — Dashboard development
- **DAX** — Measures and calculations
- **Power Query** — Data transformation and cleaning
- **Microsoft Excel** — Raw data source

---

## 🌍 Regions Covered
Toshkent, Samarqand, Andijon, Namangan, 
Farg'ona, Buxoro, Qashqadaryo

---

## 👩‍💻 Author
**Dinara**
Junior Data Analyst | Power BI Developer
📍 Tashkent, Uzbekistan
🔗 [LinkedIn](https://www.linkedin.com/in/dinara-sagdullaeva-b67740349?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=android_app) | [GitHub](https://github.com/Dinara-dev) | [hh.uz](https://hh.uz/resume/a4989dcdff0ebf1b140039ed1f455a4e673477)

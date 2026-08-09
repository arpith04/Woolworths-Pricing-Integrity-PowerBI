# Woolworths Retail & Pricing Integrity Analysis

![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-005B94?style=for-the-badge&logo=analytics&logoColor=white)
![Power Query](https://img.shields.io/badge/Power_Query-008080?style=for-the-badge&logo=microsoft&logoColor=white)

## 📌 Project Overview
This project presents an interactive **2-Page Power BI Dashboard** evaluating retail pricing compliance, promotional effectiveness, and socio-economic discount distribution across Woolworths stores in South Australia. 

The analysis specifically focuses on identifying **misleading promotions** (instances where promotional pricing lacks genuine value) and auditing whether these discrepancies disproportionately affect specific socio-economic demographics (**SEIFA classification**).

---

## 🖼️ Dashboard Preview

### Page 1: Executive Summary & Performance Overview
> *Monitors high-level KPIs, weekly revenue trends, and suburb-level pricing compliance.*

![Executive Summary](https://github.com/arpith04/Woolworths-Pricing-Integrity-PowerBI/blob/dcea9acb86bbab38f6590ac00f4f3676d8ae9181/utils/dashboard_page_1.png) 

### Page 2: Promotional & Compliance Analysis
> *Provides store-level matrix drill-downs and product-level compliance red-flagging.*

[![Promotional Analysis](https://github.com/arpith04/Woolworths-Pricing-Integrity-PowerBI/blob/dcea9acb86bbab38f6590ac00f4f3676d8ae9181/utils/dashboard_page_2.png)](https://app.powerbi.com/reportEmbed?reportId=dee8bf68-40a8-4ce2-8910-9071dbc647e1&autoAuth=true&ctid=a1b03033-8a3d-4443-a90b-0f3298ffbf90)

>👆 **Click the image above to open and interact with the live dashboard!** 

---

## 🎯 Key Business Questions & Insights
* **Revenue vs. Integrity**: Assessed total sales ($4.2M across 739K units) against pricing error frequencies.
* **Compliance Rate**: Uncovered an overall **12% Misleading Discount Rate** (~1,443 flagged promotions).
* **Demographic Breakdown**: Analyzed pricing variations across socio-economic indices (**SEIFA Advantaged vs. Disadvantaged**), identifying critical regional compliance gaps.

---

## 🛠️ Data Pipeline & Technical Implementation

### 1. Data Cleaning & Transformation (Power Query)
* Fixed regional date locale mismatches (`M/d/yyyy` vs `d/M/yyyy`) using custom locale transformations.
* Standardized column data types and handled null values across 12,000+ retail transaction records.

### 2. Data Modeling & DAX Formulas
Formulated explicit DAX measures for core metrics and conditional aggregations:
* **Total Revenue**: `Total Revenue = SUMX('Sales', 'Sales'[Units_Sold] * 'Sales'[Unit_Price])`
* **Misleading Discount Rate**: `Misleading Discount Rate (%) = DIVIDE([Misleading Promotions Count], [Total Promotions Count], 0)`

### 3. User Interface & Executive UI Design
* Built using a custom modern canvas layout (Off-white background `#F3F4F6`, rounded white card containers `#FFFFFF`, and dark navy typography `#002B49`).
* Encoded compliance alerts using visual color cues (**Red/Coral `#EF4444`**) to highlight audit flags against genuine promotions.

---

## 📁 Repository Structure
```text
├── data/
│   └── woolworths_data.csv    # Source transaction data
├── utils/
│   ├── dashboard_page1.png                # Dashboard Page 1 Screenshot
│   └── dashboard_page2.png                # Dashboard Page 2 Screenshot
├── Woolworths_PBI.pbix  # Power BI Project File
└── README.md                            # Project documentation

# LendingLens: Credit Risk Analytics Dashboard

An end-to-end Business Intelligence and predictive analytics dashboard built with **Power BI** and **Python**. This project analyzes a synthetic portfolio of 12,000+ loan records to evaluate portfolio health, identify default risk drivers, and visualize regional exposure. 

It bridges the gap between traditional BI reporting and data science by integrating **Scikit-Learn** directly into Power BI to generate machine learning feature importance charts.


## 📑 Table of Contents
- [Dashboard Architecture](#dashboard-architecture)
- [Key Business Insights](#key-business-insights)
- [Technical Stack & Features](#technical-stack--features)
- [Data Schema](#data-schema)
- [How to Reproduce](#how-to-reproduce)
- [Data Quality & Limitations](#data-quality--limitations)

---

## 📊 Dashboard Architecture

The report is structured across four interactive pages, designed to take the user from high-level executive KPIs to deep-dive predictive analytics:

### Page 1: Portfolio Health & Risk Exposure Summary
*The executive overview.* Features dynamic KPI cards (Total Loans, Portfolio Value, Default Rate) and interactive slicers. Includes a "Default Rate by Region" bar chart and a 100% stacked bar chart showing portfolio exposure by loan purpose and status.

### Page 2: Regional Exposure & Risk Heatmap
*Geographic and categorical risk analysis.* Utilizes a **Treemap** to visualize loan amount concentration by region. Features a custom **Matrix Heatmap** with conditional formatting to instantly highlight high-risk combinations of Loan Purpose and Region.

### Page 3: Risk Driver Analytics & Customer Segmentation
*The "Why" behind the defaults.* Tracks "Total Capital at Risk" and analyzes the impact of Debt-to-Income (DTI) ratios on loan status. Includes a custom Correlation Matrix to visualize relationships between financial variables (Income, Credit Score, Interest Rate).

### Page 4: Machine Learning Insights (Python Integration)
*Advanced predictive analytics.* Leverages Power BI's native Python visual scripting to run a **Random Forest Classifier**. 
- **Feature Importance Chart:** Identifies that *Interest Rate* and *Debt-to-Income Ratio* are the strongest predictors of loan default, outweighing raw loan amounts.
- **Statistical Plots:** Includes Violin plots for credit score distribution and pair-plot relationship networks.

---

## 💡 Key Business Insights

1. **Affordability Over Amount:** The ML model reveals that loan defaults are driven primarily by *Interest Rates* and *Debt-to-Income Ratios*, rather than the absolute *Loan Amount*. 
2. **Regional Concentration:** The Treemap analysis highlights significant portfolio exposure in specific regions, necessitating localized risk-adjusted pricing strategies.
3. **Digital & Unsecured Risk:** Unsecured loan types (Personal and Business loans) show higher default intensities compared to secured assets like Home Loans.

---

## ️ Technical Stack & Features

- **Business Intelligence:** Power BI Desktop (DAX, Power Query, Data Modeling)
- **Advanced Analytics:** Python (Pandas, Scikit-Learn, Matplotlib, Seaborn)
- **Data Visualization:** Custom Tooltips, Conditional Formatting (Heatmaps), Treemaps, Violin Plots
- **DAX Engineering:** Time-intelligence functions, complex aggregations, and risk-exposure calculations.

---

## 🗄️ Data Schema

The analysis is built on a comprehensive banking dataset (`Banking_Credit_Risk_Dataset.csv`) containing 22 features per loan record:

| Category | Features |
| :--- | :--- |
| **Demographics** | Age, Gender, Marital Status, Education Level, Employment Type |
| **Financials** | Annual Income, Account Balance, Existing Loans Count, Dependents |
| **Loan Details** | Loan Purpose, Loan Amount, Term (Months), Interest Rate, DTI Ratio |
| **Risk & Status** | Credit Score, Region, Loan Status (Approved/Default), Default Risk Flag |

---

## 🚀 How to Reproduce

### Prerequisites
- Power BI Desktop (Latest Version)
- Python 3.8+ installed on your machine
- Required Python libraries: `pandas`, `matplotlib`, `seaborn`, `scikit-learn`

### Steps
1. Clone this repository.
2. Open `Credit_Portfolio_Monitoring.pbix` in Power BI Desktop.
3. **Enable Python Visuals:** If prompted, ensure your Python home directory is set in *File > Options and settings > Options > Python scripting*.
4. Click **Refresh** to load the data and render the Python ML visuals on Page 4.
5. Use the Region and Loan Purpose slicers on Page 1 to interact with the dashboard.

---

## ⚠️ Data Quality & Limitations

- **Synthetic Data:** This dataset is synthetically generated for portfolio demonstration purposes. 
- **Class Imbalance:** The data generator produced a ~99% default rate. In a production environment, I would flag this as a critical data quality issue and apply techniques like SMOTE (Synthetic Minority Over-sampling Technique) or undersampling to build a balanced, unbiased predictive model.
- **Correlation vs. Causation:** The correlation matrix highlights statistical relationships but does not prove causal links between variables like Income and Default rates.

---


*Built to demonstrate end-to-end data analytics, BI dashboarding and applied machine learning capabilities.*

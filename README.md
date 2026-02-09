# Predictive-Credit-Risk-Portfolio-Profitability-Analysis
This project performs a comprehensive risk assessment of a retail loan portfolio using a dataset of ~9,500 loans. The goal is to identify key predictors of loan default and calculate the potential risk-adjusted profitability of the portfolio.

## Project Overview

This project performs a comprehensive risk assessment of a retail loan portfolio using a dataset of ~9,500 loans. As a math-focused analysis, it bridges the gap between raw financial metrics (FICO, DTI, Revolving Credit) and business decision-making. The goal is to identify key predictors of loan default and calculate the potential risk-adjusted profitability of the portfolio.

## Tools Used

* **Excel:** Data cleaning, Feature Engineering, Pivot Tables.
* **Financial Logic:** Weighted Risk Scoring, Sensitivity Analysis.
* **Statistics:** Correlation matrices, Log-normal distributions, and Descriptive Statistics.

## Key Features & Analytical Steps

### 1. Data Engineering & Cleaning

* **Income Normalization:** Converted `log_annual_inc` back to its original currency value using  to audit for outliers.
* **Audit Flags:** Created automated flags for "High Utilization" (Revolving Utilization > 30%) and "Public Record History" to isolate high-risk segments.

### 2. Quantitative Risk Modeling

Instead of relying solely on FICO scores, I developed a **Weighted Risk Grade (WRG)** using the following formula:

$$WRG = (dti \times 0.4) + (revol.util \times 0.3) + (inq.last.6mths \times 0.3)$$

This model accounts for the borrower's debt burden, credit hunger, and current credit usage simultaneously.

### 3. Financial Insights

* **Default Analysis:** Discovered that certain loan purposes (e.g., small business) carry a significantly higher `not_fully_paid` rate regardless of FICO score.
* **Correlation Study:** Used `=CORREL()` to analyze the relationship between interest rates and risk metrics, validating that higher-risk borrowers are correctly being charged higher premiums.

## Dashboard Preview

The final Excel deliverable includes an interactive dashboard featuring:

* **Slicers** for `purpose` and `credit_policy`.
* **FICO Distribution Histogram** to visualize the credit quality of the borrower pool.
* **Default Heatmap** showing which categories contribute most to portfolio loss.

## What I Learned (Fintech Focus)

* **Imbalanced Data:** Learned how to analyze "rare events" (defaults) in a sea of successful payments.
* **Risk vs. Reward:** Understanding that a "high-risk" loan isn't necessarily a bad loan for a bank, provided the `int_rate` compensates for the probability of `not_fully_paid`.
* **Regulatory Thinking:** Practiced "Model Explainability" by using transparent, weighted formulas rather than black-box methods.

---

### How to Navigate this Repo

* `/loan_data`: Contains the raw Lending Club dataset.
* `/Analysis`: The Excel Workbook with all formulas, pivot tables, and the final dashboard.
* `/Report`: A brief PDF summary of the findings and business recommendations.


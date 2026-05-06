# Telco Customer Churn Analysis Dashboard - README

This repository contains the **FUTURE_DS_02.pbix** Power BI dashboard, developed for the **Data Science & Analytics Internship** at **Future Interns**. The project aims to provide a deep dive into customer retention and churn behavior for a telecommunications company.

## Project Overview
The "Telco Customer Churn" project focuses on identifying patterns in customer attrition to help business stakeholders implement proactive retention strategies. By analyzing demographic data, service usage, and contract details, this dashboard highlights the primary drivers of churn.

## Dataset Information
The analysis utilizes the **Telco Customer Churn** dataset from Kaggle.
* **Target Variable**: `Churn` (Whether the customer left within the last month).
* **Demographics**: Gender, age range, and if they have partners/dependents.
* **Services**: Phone, multiple lines, internet, online security, online backup, device protection, tech support, and streaming TV/movies.
* **Account Info**: Tenure, contract type, payment method, paperless billing, monthly charges, and total charges.

## Dashboard Structure & Visuals
The dashboard is structured to provide both high-level metrics and granular details:

### 1. Executive Summary (KPIs)
* **Total Customers**: Total count of unique customer IDs.
* **Churn Rate**: Percentage of customers who have churned.
* **Total Revenue Loss**: Sum of `TotalCharges` for churned customers.
* **Average Tenure**: Average number of months customers stay with the company.

### 2. Customer Demographics
* **Churn by Gender & Senior Citizen Status**: Analyzes if specific age or gender groups are more prone to leaving.
* **Partner & Dependent Status**: Visualizes the impact of household stability on loyalty.

### 3. Service & Contract Analysis
* **Churn by Contract Type**: Typically highlights that "Month-to-month" contracts have significantly higher churn rates compared to one- or two-year contracts.
* **Internet Service Impact**: Compares churn rates between Fiber Optic, DSL, and No Internet service users.
* **Service Add-ons**: A heatmap or bar chart showing churn rates among customers with/without Online Security, Tech Support, or Online Backup.

### 4. Financial & Tenure Insights
* **Tenure vs. Churn**: A line or area chart showing how churn risk decreases as customer tenure increases.
* **Monthly Charges Distribution**: Analyzes whether higher monthly bills correlate with increased churn.

## Technical Implementation
* **Data Modeling**: Created a robust star schema within the Power BI Data Model.
* **Power Query (ETL)**: 
    * Cleaned missing values in the `TotalCharges` column.
    * Transformed `SeniorCitizen` from binary ($0/1$) to text ("Yes/No").
    * Categorized `Tenure` into groups (e.g., $0-12$ months, $12-24$ months).
* **DAX Measures**:
    * `Churn Rate % = DIVIDE(CALCULATE(COUNT(CustomerID), Churn="Yes"), COUNT(CustomerID))`
    * `Total Revenue = SUM(TotalCharges)`

## Key Insights
* **Contract Sensitivity**: Customers on month-to-month contracts are the most likely to churn.
* **Technical Support**: Customers without technical support services show a higher propensity to leave.
* **Tenure Milestone**: Churn is highest in the first $6$ months of service, suggesting the need for a stronger onboarding process.

## Requirements
* [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (Latest version recommended).
* Telco Customer Churn dataset (CSV format).

## How to Use
1.  Open **FUTURE_DS_02.pbix** in Power BI Desktop.
2.  Use the **Slicers** (Contract, Gender, Payment Method) to filter the data.
3.  Interact with the visuals to cross-highlight related data points and uncover specific churn segments.

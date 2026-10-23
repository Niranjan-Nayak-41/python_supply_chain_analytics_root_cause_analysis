# # Supply Chain Performance Analysis – DataCo

## Project Overview

This project analyzes the DataCo Supply Chain dataset to evaluate order fulfillment performance, identify late delivery patterns, investigate operational bottlenecks, and understand the relationship between delivery delays and profitability.

Using Python-based Exploratory Data Analysis (EDA), the project examines delivery performance across regions, customer segments, shipping modes, departments, order types, and time periods. A Random Forest classification model is also developed to predict late delivery risk.

## Business Objectives

- Analyze late delivery rates and order fulfillment performance.
- Identify operational bottlenecks across regions, shipping modes, customer segments, and departments.
- Investigate the relationship between delivery delays and order profitability.
- Analyze delivery trends by month, day of the week, and order hour.
- Build a machine learning model to classify late delivery risk.

## Tools and Technologies

- **Python:** Pandas, NumPy
- **Data Visualization:** Matplotlib, Seaborn
- **Machine Learning:** Scikit-learn, Imbalanced-learn (SMOTE)
- **Environment:** Jupyter Notebook

## Data Preparation

The original dataset contained **180,519 records and 53 columns**. Data preparation involved removing irrelevant columns, filtering shipping-canceled records, and checking missing values and duplicate records.

The resulting analysis dataset contained **172,765 records and 20 original columns**, with additional engineered features created for delivery delay, order processing time, order month, order day, order hour, and profitability classification.

## Key Business Findings

| KPI | Result |
|---|---:|
| Records analyzed | 172,765 |
| Delayed orders, based on calculated delay | 94,523 |
| Late delivery rate | 54.71% |
| On-time or early delivery rate | 45.29% |
| 90th-percentile delay among delayed orders | 3 days |
| Profitable orders | 80.66% |
| Loss-making orders | 18.69% |
| Break-even orders | 0.65% |
| Sum of positive order-level profit values | $7.5M |
| Sum of order-level profit values for delayed orders | $2.1M |

*Note: Delivery delay KPIs are based on the calculated difference between actual order processing time and scheduled shipment time. The monetary figures are sums of order-level profit values, not independently established estimates of losses caused by delays.*

## Analysis Performed

### 1. Exploratory Data Analysis
- Examined dataset structure, data types, missing values, and duplicate records.
- Analyzed categorical distributions, including payment types, delivery status, and shipping schedules.
- Created additional features to measure delivery performance and classify profitability.

### 2. Delivery Delay and Profitability Analysis
- Evaluated the distribution of early, on-schedule, and delayed orders.
- Compared order counts, average profit, and aggregate order-level profit across delay durations.
- Classified orders into profitable, loss-making, and break-even categories.

### 3. Operational Bottleneck Analysis
Compared late delivery rates across:
- Order regions
- Customer segments
- Shipping modes
- Order statuses
- Payment types
- Departments

This analysis helps identify the operational groups that warrant further investigation and targeted process improvements.

### 4. Root Cause Analysis
Investigated potential contributors to delivery delays by comparing shipping mode, customer segment, department, payment type, and order status within individual regions.

The objective was to narrow down high-delay combinations and support more targeted operational decisions.

### 5. Time-Series Analysis
Analyzed delivery delay percentages by:
- Month of order placement
- Day of the week
- Hour of the day

These comparisons help identify temporal patterns that can inform staffing, capacity planning, and fulfillment scheduling.

### 6. Machine Learning – Late Delivery Risk Prediction
Developed a Random Forest classifier to predict the `Late_delivery_risk` target using shipment schedules, order characteristics, customer segments, departments, regions, shipping modes, and time-based features.

The workflow included:
- Frequency encoding of categorical features
- An 80/20 stratified train-test split
- SMOTE to balance the training data
- Random Forest model training and evaluation

**Model performance:**

| Metric | Result |
|---|---:|
| Accuracy | 74% |
| Recall | 75% |
| Precision — late-risk class | 79% |
| F1-score — late-risk class | 77% |

The model demonstrates a useful baseline for identifying orders at risk of late delivery. Further validation and feature-engineering improvements may help improve predictive performance.

## Overall Conclusion

The analysis highlights delivery reliability as an important operational challenge, with **54.71% of analyzed orders classified as delayed** using the calculated delay metric. Profitability analysis shows that most orders were profitable, while a substantial minority generated negative order-level profit.

The project combines descriptive analytics, bottleneck investigation, time-series analysis, and machine learning to provide a structured view of supply chain performance. These findings can help businesses prioritize delivery improvement initiatives, investigate high-risk operational segments, and develop more proactive shipment monitoring strategies.

## Repository Contents

- `EDA(2).ipynb` — Exploratory data analysis, visualizations, business KPI calculations, root cause investigation, time-series analysis, and Random Forest modeling.
- `dataset/` — Dataset files, if included in the repository.

1. Overview

  This deliverable initiates a four-phase data-mining project designed to develop data-driven insights and predictive models. 
  The dataset contains information on direct marketing campaigns conducted by a Portuguese banking institution. 
  The goal is to explore, clean, and analyze the data to build a reliable foundation for modeling, clustering, and association rule mining in later stages.

2. Dataset Summary

  Source: UCI Machine Learning Repository – Bank Marketing (Additional) dataset.

  Size: 41,188 records × 21 columns (20 predictors + 1 target).

  Target Variable: y – Indicates whether the client subscribed to a term deposit (yes or no).

  Feature Types:

    Demographic: age, job, marital, education, default, housing, loan

    Campaign/Contact: contact, month, day_of_week, duration, campaign, pdays, previous, poutcome

    Macroeconomic Indicators: emp.var.rate, cons.price.idx, cons.conf.idx, euribor3m, nr.employed

    Rationale: This dataset meets all project requirements (≥8 attributes, ≥500 records) and supports all upcoming tasks — regression, classification, clustering, and association rules.

3. Data Cleaning Summary

  Removed 12 duplicate rows.

  Converted sentinel pdays = 999 into a boolean flag prev_contacted and replaced those values with NaN in pdays.

  Retained 'unknown' values in categorical columns as explicit categories for baseline analysis.

  Standardized categorical strings and verified consistent datatypes.

  Documented data leakage in duration (used only for EDA, not for predictive modeling).

  Saved cleaned baseline dataset as bank_marketing_clean_baseline.csv.

4. Exploratory Data Analysis (EDA)

  Target Distribution:

    y = yes → 11.27% of clients subscribed → indicates class imbalance.

  Distributions:

    campaign, duration, and previous are right-skewed.

    Macroeconomic indicators (euribor3m, emp.var.rate, nr.employed) show strong correlation → collinearity detected.

  Categorical Insights:

    Higher subscription rate via cellular contact (14.7%) than telephone (5.2%).

    poutcome=success has the highest conversion (~65%).

    Month and day patterns suggest time-related campaign success variation.

  Outliers: Limited but observable; handled visually using boxplots and robust scaling plans for later models.

5. Key Insights & Decisions

  Created prev_contacted to capture prior engagement, an important predictor.

  Retained “unknown” values to preserve signal integrity.

  Excluded duration from future predictive modeling due to post-outcome data leakage.

  Identified strong macro-feature collinearity — PCA or feature selection planned.

  Confirmed the need for class imbalance handling using class weights or SMOTE.

6. Challenges
   Class imbalance (~11%)
   Data leakage (duration)
   Macro variable multicollinearity
   Placeholder missing values (unknown)

Citation of Dataset:
https://archive.ics.uci.edu/dataset/222/bank+marketing

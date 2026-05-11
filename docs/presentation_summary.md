# Project Presentation Summary

## Overview
This project builds a **Public Health Data Visualization System** around a **1,000,000-row Global Health Statistics dataset** with **22 columns**. Work was completed over three weeks and three sprints:
- **Week 1:** Sprint 1 — Milestones 1 & 2
- **Week 2:** Sprint 2 — Milestones 3 & 4
- **Week 3:** Sprint 3 — Milestones 5 & 6

---

## Week 1: Sprint 1 (Milestone 1 + Milestone 2)

### Concepts Learned
- Data engineering foundations: reproducible project structure, environment setup, dataset acquisition, and version control safe practices.
- Dataset understanding: schema design, feature classification, data types, and descriptive statistics for a large health dataset.
- Data quality management: auditing for missing values, duplicates, outliers, and range validation.
- Data preparation: cleaning, standardization, categorical encoding, memory optimization, and feature engineering.

### Implementation Highlights
- Built a reproducible folder structure with `data/`, `notebooks/`, and `docs/`.
- Added a shared dataset download setup using `gdown` and documented setup in `README.md`.
- Created `notebooks/load_dataset.ipynb` as the canonical entry point.
- Catalogued 22 dataset fields, grouped variables into categorical and numerical types, and computed summary statistics.
- Performed an initial data quality audit: zero missing values, zero duplicates, and valid value ranges across the dataset.
- Transformed data for analysis: cast types, standardized strings, and converted categorical fields to optimized `category` dtype.
- Engineered new analytic features such as `Severity_Index`, `DALY_Intensity`, `Vaccine_Available_Flag`, and `High_Risk_Demographic`.

---

## Week 2: Sprint 2 (Milestone 3 + Milestone 4)

### Concepts Learned
- Exploratory analysis and visualization principles: chart selection, axis scaling, and how visual design affects interpretation.
- Hypothesis-driven exploration: using charts to form questions, then validating or rejecting them with statistical tests.
- Statistical inference fundamentals: p-values, effect size, model fit, and the difference between statistical significance and practical significance.
- Analytical reporting: failure logs, validation notes, and decision-making based on both visual and quantitative evidence.

### Implementation Highlights
- Created visual analysis charts including bar charts, scatter plots, and choropleth-style geographic comparisons.
- Documented visualization limitations such as compressed y-axis ranges and misleading color gradients.
- Conducted statistical tests using Welch’s t-test, OLS regression, and effect size measures like Cohen’s d.
- Evaluated model performance with test metrics, finding low linear predictive power (R² around 0.038).
- Captured insight mismatch: visuals suggested trends that statistical tests showed were weak or practically negligible.
- Prepared a validation log that explains why some M3 interpretations were misleading and how M4 corrected them.

---

## Week 3: Sprint 3 (Milestone 5 + Milestone 6)

### Concepts Learned
- Interactive dashboard design: user personas, KPI selection, filtering, and decision-support workflows.
- Streamlit application architecture: data flow, sidebar filters, wide-layout dashboards, and tab-based analysis.
- Advanced analytics: predictive modeling with XGBoost, model explainability with SHAP, and research-level contribution.
- Scalability and validation: handling one million rows, caching, sampling, compressed storage, and performance metrics.

### Implementation Highlights
- Defined a Streamlit dashboard architecture with filters for country, disease category, year range, age group, gender, and risk toggles.
- Built KPI panels for mortality rate, recovery rate, population affected, healthcare access, and DALYs per 100,000.
- Designed dashboard tabs for Overview, Disease Trends, Geographical Analysis, Demographic Insights, and Risk Assessment.
- Added a predictive analytics module using an XGBoost regressor to forecast mortality rates.
- Integrated explainable AI with SHAP to surface feature importance and explain model predictions.
- Outlined a research report structure with Abstract, Methodology, Results, Discussion, and Future Work.

---

## Key Takeaways
- Week 1 built the foundation: clean, reproducible data and engineered features.
- Week 2 tested insights: visual exploration plus statistical validation to avoid misleading conclusions.
- Week 3 delivered the product: an interactive dashboard and explainable predictive model for decision support.

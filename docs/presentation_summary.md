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

---

## Week 1–7 Curriculum Alignment
This project is implemented fully in Python and aligns with the Weeks 1–7 curriculum by translating each weekly theme into concrete code, analysis, and dashboard behavior.

### Week 1: Interactive Computing and Development Environments
- The project runs as a live Streamlit app in `dashboard/webapp.py`, turning a Python script into an interactive analytics environment.
- It uses `st.sidebar`, `st.tabs`, `st.markdown`, and `st.plotly_chart` for interactive output, matching the interactive computing focus of Week 1.
- Runtime controls include caching decorators (`@st.cache_data`, `@st.cache_resource`), error handling through `st.error()` and `st.stop()`, and dataset loading feedback with `st.spinner()`.
- Project documentation lives in `README.md`, `docs/`, and notebook guides, reflecting the emphasis on documentation and reproducible workflows.

### Week 2: Numerical Computing with NumPy
- The app imports `numpy as np` and uses NumPy-style sampling for large dataset visualization (`dff.sample(min(50000,len(dff)),random_state=42)`).
- Numeric operations appear in feature creation and plot logic, supporting efficient statistical summaries and data slicing.
- The project applies vectorized calculations across columns for metrics like `Severity_Index`, `DALY_Intensity`, and `Weighted_Time_Impact`.

### Week 3: Data Manipulation and Wrangling with pandas
- The dataset is loaded into pandas DataFrames from CSV and `.csv.gz` sources, with preprocessing in `load_data()`.
- Data wrangling includes cleaning, type handling, derived columns, and categorical transformation in Python.
- The `filter_data()` function shows selection, boolean masking, and range filtering for user-driven dashboard queries.
- GroupBy aggregations drive summary tables, KPI cards, and chart data for disease categories, countries, ages, and genders.

### Week 4: Data Storage, Access, and External Integration
- Data ingestion is handled in Python via `pandas.read_csv()` with support for compressed `.csv.gz` files.
- The project resolves file paths with `pathlib.Path`, searching `data/raw/`, `data/processed/`, and the project root for the dataset.
- While this project does not use web APIs or databases, it implements robust local file discovery and fallback logic in Python.

### Week 5: Data Visualization and Exploratory Analysis
- Visualization is built in Python with Plotly Express and Plotly Graph Objects for charts such as histograms, bars, lines, scatter plots, area charts, and box plots.
- The dashboard design includes custom Plotly themes, CSS styling, tabbed layout, KPI panels, and explanatory insight boxes.
- Exploratory analysis includes multi-faceted views of mortality, recovery, healthcare access, high-risk demographics, and disease trends.

### Week 6: Time Series, Financial, and Applied Analytics
- The dashboard supports time-based exploration through year-range selection and year-over-year trend charts.
- Analysis of temporal health metrics appears in annual aggregations and trend comparisons across disease categories.
- Risk assessment sections use derived time-aware scores and temporal group summaries to highlight changes over time.

### Week 7: Machine Learning and Advanced Data Science Methods
- The app includes a predictive modeling section with model loading from `models/mortality_predictor.pkl` using `joblib`.
- It presents XGBoost feature importances and SHAP-style explainability insights in Python-generated charts.
- Live prediction controls allow users to adjust features and compute a mortality prediction either via the loaded model or an analytical fallback calculation.

### Implementation Notes
- Files involved: `dashboard/webapp.py`, `docs/presentation_summary.md`, `README.md`, `notebooks/*.ipynb`, and dataset files under `data/`.
- The project emphasizes Python-based implementation for every stage: data loading, wrangling, visualization, interaction, and model inference.
- This makes the work a direct Python analog to Weeks 1–7, with the curriculum topics encoded as application features and analysis workflows.

---

## Implementation Reference
Use these files and code sections for quick presentation or Q&A.

- `dashboard/webapp.py`
  - `load_data()` and initial preprocessing: dataset loading, `.csv` / `.csv.gz` fallback, derived feature engineering, and caching. (Milestone 1 / Milestone 2)
  - `with st.sidebar:` block: sidebar filters and user inputs for country, disease, year, age group, gender, severity, and risk toggles. (Milestone 5)
  - `filter_data()` function: data selection logic, boolean filtering, and range filtering for dashboard interactivity. (Milestone 5)
  - Tab sections `tab1` through `tab6`: chart generation, KPI cards, exploratory analysis, geographic/demographic views, risk assessment, and prediction insights. (Milestones 5 & 6)
  - Prediction block: `load_model()`, XGBoost model loading with `joblib`, live predictor inputs, model inference, and analytical fallback logic. (Milestone 6)

- `data/raw/Global Health Statistics.csv`
  - Primary raw dataset for project analysis and dashboard input. (Milestones 1 & 2)

- `data/processed/global_health_enriched.csv.gz`
  - Optional compressed processed dataset used for faster app loading when available. (Milestones 1 & 2)

- `notebooks/load_dataset.ipynb`
  - Core Python notebook for initial dataset import, cleaning, inspection, and feature analysis. (Milestones 1 & 2)

- `notebooks/milestone2_data_processing_transformation.ipynb`, `notebooks/milestone3_visualization_exploratory_analysis.ipynb`, `notebooks/milestone4_statistical_inference_analytical_modeling.ipynb`, `notebooks/milestone5_interactive_visual_analytics_system.ipynb`
  - Milestone notebooks that show detailed Python analysis steps and results for each phase. (Milestones 2–5)

- `docs/milestone1_foundations.md`, `docs/milestone2_data_processing_transformations.md`, `docs/milestone3_visualization_exploratory_analysis.md`, `docs/milestone4_statistical_inference_analytical_modelling.md`
  - Written documentation supporting each milestone, useful for answering process and design questions. (Milestones 1–4)

- `README.md`
  - Project setup, running instructions, and high-level overview for presenters and reviewers. (Project-wide / all milestones)

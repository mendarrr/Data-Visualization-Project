# Milestone 2: Data Processing & Transformation

**Project:** Public Health Data Visualization System  
**Dataset:** Global Health Statistics (1,000,000 records × 22 columns)  
**Period:** April 20–27, 2026  
**Status:**  Complete  

---

## Executive Summary

Milestone 2 develops a robust, reproducible data processing pipeline that cleans, transforms, and engineers features from the raw dataset. The phase includes data quality auditing, cleaning operations, standardization, and feature engineering to prepare the dataset for analysis and visualization.

---

## 1. Project Setup

### Libraries Used

| Library | Purpose |
|---------|---------|
| `pandas` | Data loading, exploration, and manipulation |
| `numpy` | Numerical operations and array handling |
| `os` | Operating system interactions |
| `pathlib` | Cross-platform file path handling |

### Environment

- **Python Version:** 3.12.7
- **Virtual Environment:** `.venv`
- **IDE:** Visual Studio Code
- **Repository:** Feature branch `feature/milestone2-pipeline`

---

## 2. Data Loading Strategy

### File Path Resolution

The pipeline implements **reproducible, machine-independent file paths** using `pathlib.Path`:

```python
project_root = Path().resolve().parent if Path().resolve().name == 'notebooks' else Path().resolve()
data_path = project_root / "data" / "raw"
```

**Key Design Decision:** No hardcoded absolute paths (`C:\Users\...`). This ensures the code runs identically on any machine, regardless of installation location or OS (Windows/Mac/Linux).

### Data Loading Results

-  Dataset located: `data/raw/Global Health Statistics.csv`
-  Successfully loaded: **1,000,000 rows × 22 columns**
-  Format: CSV (Comma-Separated Values)
-  Accessible from all environments

---

## 3. Data Quality Audit

### Audit Methodology

A comprehensive quality audit was performed to assess data **structure**, **completeness**, and **reliability** before any transformation operations.

### Audit Checks Performed

| Check | Purpose | Findings |
|-------|---------|----------|
| **Shape** | Verify dataset dimensions and feature count | 1,000,000 rows × 22 columns confirmed |
| **Data Types** | Ensure correct storage types for numerical/categorical data |  No type issues detected |
| **Missing Values** | Identify incomplete data requiring attention |  Zero missing values |
| **Duplicate Rows** | Detect repeated records |  Zero duplicates found |
| **Range Validation** | Check for out-of-bounds values in percentage/rate columns |  All values within expected ranges |
| **Negative Values** | Identify impossible negative counts/percentages |  No invalid negatives |
| **Outliers** | Detect statistical anomalies using IQR method |  Outliers identified and documented |
| **Categorical Consistency** | Verify unique values in categorical columns |  Consistent unique values per column |

### Key Audit Results

| Metric | Result |
|--------|--------|
| Missing Values | 0% |
| Duplicate Rows | 0 |
| Data Type Errors | 0 |
| Out-of-Range Values | 0 (all within expected bounds) |
| **Overall Data Quality** | **EXCELLENT** |

---


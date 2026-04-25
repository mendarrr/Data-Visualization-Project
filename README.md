# Public Health Data Visualization System
An end-to-end visual analytics pipeline built on the **Global Health Statistics** dataset (1,000,000 records with ).  
Developed progressively across six milestones as part of a group data visualization project.

---

## Project Structure

```
Data-Visualization-Project/
├── data/
│   ├── raw/                  # Contains the Original Dataset
│   │   └── DATA_SOURCE.md    # Our shared Google Drive link to download the dataset
│   └── processed/            # Cleaned/transformed outputs from the milestone pipelines deliverables
├── notebooks/
│   ├── load_dataset.ipynb    # Always run this before any other notebook to load the dataset locally
│   ├── milestone1_foundations.ipynb
│   ├── milestone2_pipeline.ipynb
│   ├── milestone3_visualization.ipynb
│   ├── milestone4_statistics.ipynb
│   ├── milestone5_dashboard.ipynb
│   └── milestone6_research.ipynb
├── docs/
│   ├── charts/               # Saved Charts and Plots
│   ├── data_schema.md        # Variable definitions and types
│   └── data_quality_report.md # For Quality Assessment Deliverables
├── .gitignore
├── requirements.txt
└── README.md
```

---

## Dataset

- **Name:** Global Health Statistics
- **Size:** 1,000,000 rows × 22 columns
- **Source:** [Google Drive Folder](https://drive.google.com/drive/folders/1MmV6mQYdxmTR9UXO5maEgoEn_R1Y2vdW)
- **Key variables:** Country, Year, Disease Name, Disease Category, Mortality Rate, Healthcare Access, Recovery Rate, Per Capita Income, and etc.

> Our raw csv is excluded from git because it has a storage capacity of > 100MB

---

## Project Setup

### 1. Clone the repo
```bash
git clone <git@github.com:mendarrr/Data-Visualization-Project.git>
cd Data-Visualization-Project
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

### 3. Get the dataset
Download `Global Health Statistics.csv` from the [Google Drive link](https://drive.google.com/drive/folders/1MmV6mQYdxmTR9UXO5maEgoEn_R1Y2vdW) and place it in `data/raw/`.  
Or just run `notebooks/load_dataset.ipynb` — it will download it for you if the file is missing (Alternative to cater for difference in working environments ie Windows/Ubuntu)

### 4. Run the loader
Open and run `notebooks/load_dataset.ipynb` to verify your environment is connected correctly before starting any milestone work... Ensure you change the kernel to Python Dataviz in your IDE (VS Code)

---

## Milestones

| # | Title | Notebook | Status |
|---|-------|----------|--------|
| 1 | Data Representation & Foundations | `milestone1_foundations.ipynb` | 🔲 |
| 2 | Data Processing & Transformation | `milestone2_pipeline.ipynb` | 🔲 |
| 3 | Visualization & Exploratory Analysis | `milestone3_visualization.ipynb` | 🔲 |
| 4 | Statistical Inference & Analytical Modeling | `milestone4_statistics.ipynb` | 🔲 |
| 5 | Interactive Visual Analytics System | `milestone5_dashboard.ipynb` | 🔲 |
| 6 | Research Contribution & Advanced Analytics | `milestone6_research.ipynb` | 🔲 |

---

## Team Workflow

- Each member works on a **named feature branch**: `name/milestone1-task`, `name/milestone2-task`, etc.
- Never commit directly to `main`.... Instead, In your IDE Terminal:
- `git pull origin main .` # First Step always when you begin the days work
- `git checkout -b your_branch_name` # This is you entering your own branch in your local machine... after completing and checking that it is error free:
- `git add .`
- `git commit -m "Explain whatever changes you've made in a brief message"`
- `git push origin your_branch_name`
- > The above steps will be repeated as you do your project and make whatever changes
- **End of the Day Merging**: Will be done with all members present using:
- `git checkout -b main`
- `git merge your_branch_name`
  
- **Never** push files from `data/raw/` or `data/processed/` to GitHub.
- No Folder or file to be added... Use the Existing Ones
- Open a Pull Request and tag the team lead for review before merging.
 
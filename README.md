# Public Health Data Visualization System

An end-to-end visual analytics pipeline built on the **Global Health Statistics** dataset (1,000,000 records with 22 fields).  
Developed progressively across six milestones as part of a group data visualization project.

---

## Project Structure

```
Data-Visualization-Project/
├── data/
│   ├── raw/                  # Original dataset — NOT pushed to GitHub
│   │   └── DATA_SOURCE.md    # Google Drive link to download the dataset
│   └── processed/            # Cleaned/transformed outputs from milestone pipelines
├── notebooks/
│   ├── load_dataset.ipynb    # Always run this first before any milestone notebook
│   ├── milestone1_foundations.ipynb
│   ├── milestone2_pipeline.ipynb
│   ├── milestone3_visualization.ipynb
│   ├── milestone4_statistics.ipynb
│   ├── milestone5_dashboard.ipynb
│   └── milestone6_research.ipynb
├── docs/
│   ├── charts/               # Saved chart outputs
│   ├── data_schema.md        # Variable definitions and types
│   └── data_quality_report.md
├── .gitignore
├── requirements.txt
└── README.md
```

---

## Dataset

- **Name:** Global Health Statistics
- **Size:** 1,000,000 rows × 22 columns
- **Source:** [Google Drive Folder](https://drive.google.com/drive/folders/1MmV6mQYdxmTR9UXO5maEgoEn_R1Y2vdW)
- **Key variables:** Country, Year, Disease Name, Disease Category, Mortality Rate, Healthcare Access, Recovery Rate, Per Capita Income, and more.

> The raw CSV is excluded from Git (>100MB). Follow the setup steps below to download it.

---

## First-Time Setup (Run Once After Cloning) => Cloning is done after forking the repository from repo owner
### Step 1 — Clone the repo
```bash
git clone git@github.com:mendarrr/Data-Visualization-Project.git
cd Data-Visualization-Project
```
### Step 2 — Create the virtual environment

**Ubuntu/Mac:**
```bash
python3 -m venv .venv
source .venv/bin/activate
```

**Windows:**
```bash
python -m venv .venv
.venv\Scripts\activate
```
> Your terminal prompt should now show `(.venv)` — this means the environment is active.

### Step 3 — Install dependencies
```bash
pip install -r requirements.txt
```

### Step 4 — Register the Jupyter kernel
```bash
python -m ipykernel install --user --name=dataviz --display-name "Python (dataviz)"
```

### Step 5 — Download the dataset

**Ubuntu/Mac:**
```bash
python -c "import gdown; gdown.download('https://drive.google.com/uc?id=1cug4qWE6qFArHmYwcXUdDMaJIfmUzAZD', 'data/raw/Global Health Statistics.csv', quiet=False)"
```

**Windows:**
```bash
python -c "import gdown; gdown.download('https://drive.google.com/uc?id=1cug4qWE6qFArHmYwcXUdDMaJIfmUzAZD', 'data/raw/Global Health Statistics.csv', quiet=False)"
```
> Same command for both — Note => just make sure your `.venv` is active first.

### Step 6 — Select the kernel in VS Code
1. Open any `.ipynb` notebook in VS Code
2. Click the kernel selector (top right corner)
3. Select **Python (dataviz)**

### Step 7 — Verify everything works
Open and run `notebooks/load_dataset.ipynb` — it should print:
```
All checks passed. Dataset is ready.
```

---

## Daily Workflow (Every Time You Work)
### Activate the virtual environment first
**Ubuntu/Mac:**
```bash
source .venv/bin/activate
```
**Windows:**
```bash
.venv\Scripts\activate
```

### Then sync with main before starting
```bash
git pull origin main --rebase
```

### Create your named feature branch if you haven't already
```bash
git checkout -b yourname/milestone1-task
```

### Save and push your work
```bash
git add .
git commit -m "Brief description of what you did"
git push origin yourname/milestone1-task
```

> Then open a Pull Request on GitHub and tag the team lead (Repo owner) for review before merging.

---

## Rules

- Never commit directly to `main`
- Never push files from `data/raw/` or `data/processed/`
- Never add new folders or files — use the existing structure only
- End-of-day merging is done with all members present

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

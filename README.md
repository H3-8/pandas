# pandas

> Notes and examples for learning Python data analysis with **pandas** — mainly through a hands-on exploratory notebook.

## What’s in this repo (current)
- `notebook.ipynb`: exploratory analysis on an orders dataset (loaded from an Excel file)
- `data/`: data folder (expects an Excel file, see below)
- `README.md`: setup + instructions

## Quickstart

### Option A: `pip` + `venv`
```bash
python -m venv .venv
# macOS/Linux:
source .venv/bin/activate
# Windows (PowerShell):
.\.venv\Scripts\Activate.ps1
# Windows (cmd.exe):
.\.venv\Scripts\activate.bat

pip install -r requirements.txt
```

### Option B: conda
```bash
conda create -n pandas-env python=3.11
conda activate pandas-env
pip install -r requirements.txt
```

## Requirements
- Python **3.10+**
- pip (or conda)
- Jupyter (recommended)

> If you don’t have a `requirements.txt` yet, create one with at least: `pandas`, `numpy`, `matplotlib`, `seaborn`, `openpyxl`.

## Dataset expected by the notebook
The notebook reads an Excel file here:

- `data/dataset_exercices.xlsx`
- sheet name: `commandes`

So you should have:
```text
data/
└── dataset_exercices.xlsx
```

### Columns used
The notebook expects columns like:
- `pays`, `categorie`, `statut`
- `date_commande` (datetime-like)
- `quantite`, `prix_unitaire`, `total_achat`
- `note_satisfaction`
- plus basic client fields (`client_id`, `prenom`, `nom`, `age`, `ville`)

## Usage

### Run the notebook
```bash
jupyter lab
```
Then open `notebook.ipynb`.

## What the notebook covers
The analysis is a progressive EDA workflow:
- Import libraries: **pandas**, **numpy**, **matplotlib**, **seaborn**
- Load Excel data with `pd.read_excel(..., sheet_name="commandes")`
- First look: `df.head()`, `df.columns`, `df.describe()`, `df["pays"].unique()`
- Feature engineering:
  - `month` extracted from `date_commande`
  - `montant_tva` computed from `total_achat` (e.g. `total_achat * 0.2`)
- Aggregations / insights:
  - average `total_achat` by country (`groupby`)
  - per-country totals and average satisfaction (`groupby().agg(...)`)
  - top categories by revenue
  - comparisons for `Premium` status customers
  - top purchases (`nlargest`)
- Visualizations:
  - bar plot of `sum_total_achat` by country
  - scatter plot (e.g. `total_achat` vs `note_satisfaction`)
- Correlations:
  - correlation matrix on numeric columns
  - correlation ranking vs `total_achat`

## Project structure
```text
.
├── data/                 # datasets (expected: dataset_exercices.xlsx)
├── notebook.ipynb        # main notebook (EDA + groupby + plots)
└── README.md
```

## Notes
- If you publish this publicly, consider renaming the repository to avoid confusion with the official `pandas` library.
- If you want others to reuse this content, add a `LICENSE` file (MIT/Apache-2.0/etc.) and mention it here.

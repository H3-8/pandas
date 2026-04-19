# pandas

> A small collection of notes and examples for learning Python data analysis with **pandas**.

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

## What’s in this repo?
- Short, practical **pandas** examples (scripts and/or notebooks)
- (Optional) Jupyter notebooks and small datasets
- Experiments / scratch work (WIP)

## Requirements
- Python **3.10+**
- pip (or conda)

## Usage

### Notebooks
If you have notebooks in `notebooks/`:
```bash
jupyter lab
```

### Scripts
If you have runnable scripts (for example under `src/`), run them like:
```bash
python path/to/script.py
```

> Tip: If you have a single entry point (e.g., `main.py`), replace the command above with the exact command you expect people to run.

## Project structure
```text
.
├── data/                # datasets (if present)
├── notebooks/           # Jupyter notebooks (if present)
├── src/                 # reusable code / scripts (if present)
├── tests/               # tests (if present)
├── requirements.txt     # dependencies (if present)
└── README.md
```

## Notes
- If you publish this publicly, consider renaming the repository to avoid confusion with the official `pandas` library.

## License
If you want others to reuse this content, add a `LICENSE` file (MIT/Apache-2.0/etc.) and mention it here.
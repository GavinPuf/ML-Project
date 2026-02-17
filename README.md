cat > README.md <<'EOF'
# ML Class Project (Group Repo)

This GitHub repo is for collaboration (code + notebooks). The graded deliverable is the final report in `reports/` (or wherever we keep it).

## What goes where (DO THIS)
- `src/` = shared reusable code (data loading, preprocessing, models, evaluation)
- `notebooks/` = exploration/EDA/experiments (each person keeps their own notebook file)
- `reports/` = final writeup + figures that appear in the report
- `data/` = NOT stored in GitHub (see below)

## Data policy (IMPORTANT)
We use datasets for ML, but we do NOT commit large datasets to GitHub.
- Data lives in shared storage (Drive/Kaggle/etc.)
- Each person downloads data locally into `data/raw/` and/or `data/processed/`
- `data/` should stay ignored by git (except README / placeholders)

## Collaboration rules (prevents headaches)
1) Do NOT push directly to `main`.
2) Always make a branch for your work:
   git checkout -b feature/short-description
3) Each person uses their own notebook file:
   notebooks/gavin_eda.ipynb
   notebooks/owen_baseline.ipynb
   etc.

## Basic workflow (every time)
1) Get latest:
   git pull origin main

2) Create branch:
   git checkout -b feature/short-description

3) Work, then commit:
   git add .
   git commit -m "Clear description of change"

4) Push branch:
   git push -u origin feature/short-description

5) Open a Pull Request on GitHub and merge after 1 teammate reviews.

## Quick start (kept generic)
Create a venv:
  python -m venv .venv
  source .venv/bin/activate   # macOS/Linux
  .venv\Scripts\activate      # Windows

Install deps (we will fill this in later):
  pip install -r requirements.txt
EOF

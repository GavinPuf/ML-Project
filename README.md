# ML Project — NBA Pre-Game Betting Predictions

This repo is a beginner-friendly, reproducible ML pipeline for **NBA pre-game predictions** using:
- Historical NBA stats (Kaggle: historical box scores + team stats)
- Sportsbook odds (The Odds API)

**Pre-game only rule:** every feature must be known *before tipoff* to avoid leakage.

## What we’re predicting

Our primary target is the **final score** of each game. By modelling the final points scored by each team, we implicitly capture both the moneyline outcome (who wins) and the spread (point differential). We'll start with regression models for home and away scores and derive moneyline and spread probabilities from these predictions. Additional targets such as total points can be explored as extensions.

## Repo structure

- `src/` — reusable code (loading, cleaning, feature engineering, modelling, evaluation)
- `notebooks/` — EDA and experiments (each person keeps their own notebook file)
- `reports/` — final report and figures
- `data/` — not committed (see `data/README.md` for guidance)

## Data sources

### Historical stats (Kaggle)

Dataset: *Historical NBA Data and Player Box Scores* (1947–present) — includes player and team box stats and advanced metrics. We'll primarily use team-level tables such as `TeamStatisticsAdvanced.csv`, but may join additional tables as needed.

### Sportsbook odds (The Odds API)

We use The Odds API v4 endpoints to pull upcoming NBA games and odds. We'll focus on the `h2h` (moneyline) and `spreads` markets for sportsbooks in the U.S. region. The API has request limits; we'll cache responses and combine market queries where possible. See `data/README.md` for setup instructions.

## Quickstart (local)

1. Clone the repo:
   ```bash
   git clone https://github.com/GavinPuf/ML-Project.git
   cd ML-Project
   ```

2. Create and activate a Python virtual environment.

   **macOS/Linux**
   ```bash
   python -m venv .venv
   source .venv/bin/activate
   ```

   **Windows (PowerShell)**
   ```powershell
   python -m venv .venv
   .\.venv\Scripts\Activate.ps1
   ```

3. Install requirements:
   ```bash
   pip install -r requirements.txt
   ```

4. Download the Kaggle dataset and place it in `data/raw/kaggle/`. Configure your Odds API key by creating a `.env` file in the project root (see `data/README.md`).

## Collaboration workflow

- **Never commit directly to `main`.** Always create a branch: `git checkout -b feature/<short-name>` or `docs/<short-name>`.
- **Open a Pull Request** and have at least one teammate review before merging.
- Each person owns their notebook file under `notebooks/`. Avoid editing someone else’s notebook without coordination.
- For step-by-step Git and GitHub instructions, see `docs/GITHUB_FOR_BEGINNERS.md`. For contribution conventions, see `CONTRIBUTING.md`.

## Reproducibility goal

The deliverable is the final report, but we aim for full reproducibility: cloning the repo, downloading the data and running our pipeline should reproduce the key analyses and figures used in the report.

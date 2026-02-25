# Data

## IMPORTANT
WeWe do **not** commit datasets to GitHub.

Folder layout:
- `data/raw/` — original downloads (Kaggle CSVs, Odds API raw JSON)
- `data/processed/` — cleaned/merged tables used for modeling
- `data/cache/` — cached API responses (timestamped)

## Kaggle dataset
Download the Kaggle dataset ("Historical NBA Data and Player Box Scores") and place its CSV files into `data/raw/kaggle/`. We primarily use `TeamStatisticsAdvanced.csv` plus supporting tables as needed.

## The Odds API
We pull sports betting odds from The Odds API v4 endpoints. We care about moneyline (`h2h`) and spread (`spreads`) markets. See the API documentation for details.

### API key setup (do **not** commit keys)
Create a file named `.env` in the repository root:

```
ODDS_API_KEY=your_key_here
```

Never commit `.env`. It is ignored by `.gitignore` and should remain local.

### Rate limits
The Odds API rate limit is approximately 30 requests per second. Always combine markets and regions in a single request when possible. Cache responses to avoid unnecessary calls.

## Local data policy
- **Do not commit data files** to GitHub. Keep raw CSVs and cached JSON in `data/raw/` and `data/cache/` on your machine.
- **Do not edit raw data in place**. Write processed outputs to `data/processed/`.

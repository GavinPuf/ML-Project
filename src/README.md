# src — Shared Code

Goal: keep notebooks thin and put reusable logic here.

Planned modules (create as needed):
- `src/ingest/` — read Kaggle CSVs, validate schemas
- `src/odds/` — fetch Odds API + caching layer
- `src/features/` — pre-game feature engineering
- `src/models/` — training code (baseline → improved)
- `src/eval/` — metrics & backtesting utilities

Design rules:
- No hardcoded absolute paths
- Functions should accept inputs and return outputs (testable)
- Anything used by multiple notebooks belongs here

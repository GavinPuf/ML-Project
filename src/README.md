# src — Shared Code

Goal: keep notebooks thin and put reusable logic here.

Current modules in `src/`:

- `src/data/` – dataset ingestion: reading Kaggle CSVs and preparing raw data
- `src/models/` – model definitions and builders
- `src/training/` – scripts for training and evaluating models
- `src/utils/` – metrics and miscellaneous utilities

Additional modules such as `odds/`, `features/`, and `eval/` may be added as the project develops.

Design rules:
- No hardcoded absolute paths
- Functions should accept inputs and return outputs (testable)
- Anything used by multiple notebooks belongs here

# Project Plan — NBA Pre-Game Predictions

## Objective

Build a pre-game model to predict the **final score** for NBA games using historical stats and sportsbook odds, which can be translated into moneyline (win probability) and spread (point differential) betting signals. The project will culminate in a written report and codebase that enables reproducible experimentation.

## Scope decisions

- **Target**: Predict final scores for both home and away teams. Derive win probability and point spread from these predicted scores.
- **Features**: Pre-game information only (historical performance, team/player stats, injuries, betting lines available before tipoff). No in-game stats.
- **Unit of prediction**: One row per game (home and away scores predicted jointly).
- **Markets**: Use `h2h` and `spreads` odds from The Odds API to incorporate bookmaker expectations and identify value.

## Milestones

1. **Setup (Week 1)** – Team members can clone the repo, run notebooks, and understand the Git workflow. Download and inspect the Kaggle dataset. Decide on the schema for the modelling table.
2. **Data pipeline (Week 2)** – Clean and join historical team statistics into a single table indexed by game and date. Implement a time-aware train/test split to prevent leakage.
3. **Baseline modelling (Week 3)** – Build baseline regression models to predict final scores using only historical stats. Evaluate using backtesting across seasons.
4. **Odds integration (Week 3–4)** – Fetch pre-game moneyline and spread odds via The Odds API. Merge odds into the modelling dataset. Compare model performance with and without odds features.
5. **Evaluation & backtesting (Week 4)** – Define evaluation metrics for continuous score predictions (e.g., mean absolute error) and derived metrics for win probability and spread accuracy. Backtest a simple betting strategy using predicted edges vs. bookmaker odds.
6. **Final model & report (Final week)** – Select the final modelling approach. Document methodology, results, limitations, and potential future work. Compile the final report and ensure reproducibility.

## Team roles (suggested)

- **Data lead** – Responsible for cleaning and joining Kaggle data; defines the modelling table schema.
- **Odds lead** – Implements Odds API ingestion, handles rate limiting, and caches responses.
- **Modelling lead** – Develops baseline and advanced models, tunes hyperparameters, and evaluates performance.
- **Reporting lead** – Organises the final report, ensures figures and tables are clear, and coordinates writing contributions.

## Definition of done

A pull request is ready to merge when:
- Changes are small and well-described.
- Code runs on a fresh clone with only public dependencies.
- No secrets or large data files are committed.
- Tests or notebooks demonstrating functionality are included.

# reports

The graded deliverable is the final report and accompanying figures.

## Suggested structure

1. **Problem statement and target definition**
   - Clearly define what the model is predicting (final score, win probability, spread) and why it matters.

2. **Data sources and leakage policy**
   - Describe the Kaggle historical NBA dataset and The Odds API.
   - Emphasize the pre-game only rule to avoid data leakage.

3. **Feature engineering**
   - Outline how raw statistics and odds are transformed into model features.
   - Include handling of time-based features and normalization.

4. **Models and baselines**
   - Describe baseline models (e.g., linear regression for scores) and any advanced models used.
   - Explain training procedures and hyperparameter tuning.

5. **Evaluation**
   - Specify the time-based train/validation/test split (e.g., by season or date).
   - Report metrics relevant to regression and classification (e.g., MAE, RMSE, accuracy, AUC).

6. **Odds integration results**
   - Compare model performance with and without sportsbook odds features.
   - Highlight insights into how odds data improves predictions.

7. **Limitations and ethics/disclaimer**
   - Discuss assumptions, potential biases in the data, and limitations of the model.
   - Include a disclaimer that this project is for educational purposes and not financial advice.

# Week 9 – Gradient Boosting

This notebook focuses on using Gradient Boosting Regression to predict hospital length of stay (LOS). Gradient Boosting is a powerful ensemble technique that builds a series of decision trees, with each one trying to fix the mistakes of the previous one. The goal this week was to beat previous models (like KNN and Elastic Net) by tuning this flexible, high-performance model.

- Loaded and cleaned the data, replaced values like `'5+'`, and encoded categorical variables.
- Built a baseline Gradient Boosting model using default parameters.
- Tuned hyperparameters using `GridSearchCV`, including:
  - `n_estimators` (number of trees)
  - `learning_rate`
  - `max_depth`
  - `min_samples_leaf` (regularization)
- Analyzed the final model’s performance and visualized the most important features.

##  Results

- **Baseline Model:**
  - RMSE: **0.60**
  - R²: **0.93**
- **Best Model (after tuning):**
  - RMSE: **0.43**
  - R²: **0.97**
- **Best Parameters:**
  - `n_estimators = 200`
  - `learning_rate = 0.1`
  - `max_depth = 5`
  - `min_samples_leaf = 1`

##  Feature Insights

- `rcount` was the most important predictor, contributing over half of the model’s total importance.
- `facid_E` (facility ID) was also highly influential.
- Other features like `hematocrit`, `glucose`, `respiration`, and `creatinine` added useful but smaller contributions.

## Conclusion

Gradient Boosting Regression outperformed all previous models. After tuning, the final model predicted LOS with a small average error (RMSE 0.43) and explained nearly all the variance (R² 0.97). This shows how powerful boosting can be, especially when key hyperparameters are optimized.

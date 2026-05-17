Sri Lanka Daily Tourist Arrivals — Forecasting & Structural Analysis
===============================================================

Abstract
--------
Abstract—Accurately predicting daily international tourist
arrivals is challenging for tourism-dependent economies like
Sri Lanka, especially during its post-crisis recovery (2023–
2025). Existing methods often ignore non-Google search engines,
missing critical signals from key source markets like Russia,
where Yandex dominates. This paper introduces a multi-model
forecasting framework that integrates official daily arrivals with
Yandex data, localized Google Trends, exchange rates, and
weather records. We evaluate seven architectures, Pure SARIMA,
SARIMAX, XGBoost, Random Forest, LSTM, Support Vector
Regression (SVR), and a Sequential Hybrid, over a 550-day
rolling test period. To prevent data leakage, feature selection
utilizes Granger causality and cross-correlation analysis strictly
on training data. The results demonstrate that SVR with an RBF
kernel performs best, achieving a rolling MAPE of 8.94% and an
RMSE of 736 arrivals/day. Crucially, Yandex queries for tours
and flights emerge as the strongest exogenous predictor across
all machine learning models, completely outperforming Russian
Google Trends data, which proved uninformative. These findings
confirm that aligning predictive features with a tourist market’s
preferred search engine significantly enhances forecasting accu-
racy, providing highly actionable insights for modern tourism
intelligence systems.

Overview
--------
- Purpose: Short longitudinal analysis and forecasting of daily tourist arrivals to Sri Lanka (2023–2025), integrating SLTDA arrivals with weather, exchange rates, Google Trends and Yandex data.
- Approach: Data integration → leakage-safe preprocessing → structural-break detection → evidence-driven feature screening (Granger, CCF) → construct supervised matrices (V1/V2/V3) → evaluate statistical and ML forecasting architectures with rolling forecasts.

Data
----
- Source folder: `data/`
- Key files: `SLTDA Data - 2023-2025 Daily dataset.csv`, `USD_LKR_Daily_2023_2025.csv`, `Colombo_Weather_Daily_2023_2025.csv`, Google/Yandex trend exports in `data/`.

Notebook
--------
- Main analysis notebook: `CODE/Finalizednotebookwithmarkup.ipynb`

Outputs
-------
- Figures: `outputs/figures/` (structural-break diagnostics, decomposition, Granger/CCF heatmaps, model trajectories, CI bands, SHAP visuals).
- CSV artefacts: `outputs/csv/` (preprocessed panel, supervised matrices, Granger/CCF summaries, model results, feature impact tables).

Reproducibility
---------------
- Training/test split: training window ends `2024-06-29`; test period begins `2024-06-30`.
- Run the notebook top-to-bottom to reproduce preprocessing, model training, and evaluation.

Quick start
-----------
Install common dependencies (example):

```bash
python -m pip install -r requirements.txt
# or install core packages manually
pip install pandas numpy scipy matplotlib seaborn scikit-learn statsmodels xgboost tensorflow shap
```

Open and run: `CODE/Finalizednotebookwithmarkup.ipynb`

Contact
-------
For questions or improvements, reply in this workspace and I will update the README accordingly.

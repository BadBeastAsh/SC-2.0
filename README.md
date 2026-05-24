# SC-2.0 Supplier Disruption Dataset

## Overview
This dataset provides a comprehensive view of dynamic supplier disruption risk scoring across a simulated 60-day horizon (Jan 1–Mar 1, 2025) for 10 suppliers. Each row includes temporal disruption signals and pre-computed disruption risk outputs based on a fused analytical model. The model integrates a knowledge-graph (KG) supplier assessment score (`kg_score`), an NLP semantic embedding score (`Em_Score`), and five external disruption indicators: `twitter_alert`, `weather_risk`, `economic_risk`, `geo_risk`, and `tech_risk`. Operational impact is captured via `downtime_hours`, while `high_disruption_p` provides the daily probability of high disruption.

## Repository contents
- `supplier_disruption_log_table_coded.csv` — main dataset
- `casra_prediction.ipynb` — end-to-end modeling and evaluation
- `hyperparameter_tuning.ipynb` — model tuning workflow
- `shap_analysis.ipynb` — SHAP-based interpretability
- `dataset_description.docx` — detailed dataset documentation
- `xgb_supplier_disruption.joblib` — sample model artifact

## Quickstart
1. Open any notebook in Jupyter or Colab.
2. Ensure `supplier_disruption_log_table_coded.csv` is in the repo root.
3. Run the notebooks top-to-bottom.

Optional inputs:
- `supplier_list_100.xlsx` is referenced by the KG ranking section in `casra_prediction.ipynb`. Add it to the repo root if you want to run that section.

## Intended use
- **Academic research:** Disruption propagation, resilience strategies, and trade-off analysis.
- **Simulation input:** Scenarios for discrete-event or agent-based simulations.
- **ML training/benchmarking:** Disruption classification and predictive risk modeling.
- **Multi-criteria decision making:** Trade-offs among cost, risk, downtime, and sustainability.

## Recommended preprocessing
- Normalize `kg_score` and `Em_Score` for comparative model training.
- Convert binary indicators to categorical labels for dashboards.
- Apply rolling averages or exponential smoothing on `high_disruption_p` for volatility analysis.

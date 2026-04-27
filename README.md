# S-Mobile: Predicting Customer Churn

A proactive churn management framework for a telecom with ~1M subscribers —
built to move from reactive retention to predictive, data-driven intervention.

## Background

S-Mobile faced a 2% monthly churn rate. The traditional approach — waiting for
customers to call in and threaten to leave — was reactive and costly. This
project builds a full pipeline: predict who will churn, identify why, design
targeted actions, and evaluate the economics of each intervention.

## Methodology

- **Churn prediction:** Logistic Regression vs. Random Forest (tuned via
  RandomizedSearchCV); final model selected on validation AUC (~0.70)
- **Probability correction:** training data balanced at 50% churn → corrected
  back to representative 2% population rate for CLV analysis
- **Driver analysis:** Permutation Importance + Partial Dependence Plots
  identified top 5 churn drivers (occupation, equipment age, overage, credit
  rating, tenure)
- **Retention actions:** 5 targeted interventions designed, each quantified via
  model-based counterfactuals
- **CLV evaluation:** 5-year CLV model with 10% annual discount rate

## Key Results

Baseline 5-year CLV per customer: **$1,156** (at 2% monthly churn, $40/month)

| Intervention | Churn Reduction | Incremental CLV | Proposed Cost |
|---|---|---|---|
| Credit auto-pay enrollment | −0.88 pp | +$258/customer | $40–$60 |
| Early device upgrade | −0.35 pp | +$93/customer | $50–$70 |
| Plan optimization | −0.31 pp | +$82/customer | $30–$50 |

All three actions generate positive ROI under realistic cost assumptions.

## Files

- `smobile-project.ipynb`: Full analysis notebook

## Tools

Python · Polars · pyrsm · scikit-learn · Logistic Regression · Random Forest ·
Permutation Importance · Partial Dependence Plots · CLV Modeling

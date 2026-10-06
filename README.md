# Synthetic Fraud Detection Framework 🏦

Production-grade validation architecture for testing financial fraud and credit
risk models on synthetic populations. Built by Genuity IO (Feb–Apr 2026).

## The problem

Fintechs face extreme regulatory hurdles using real PII to train fraud models.
Synthetic data solves privacy but raises validation: *how do you prove synthetic
fraudsters behave like real fraudsters?* This framework answers that with
measured bounds on accuracy, false positives, and drift.

## Results (measured on 1.29M train / 555K test transactions)

- **F1 +39.1%** (0.407 → 0.566) via synthetic augmentation
- **Precision +82.6%**, PR-AUC **+17.7%**
- **False positives −67.2%** (3,338 → 1,094); −89.2% at threshold 0.85
- **58,338 synthetic fraud records** across 6 scenarios, **0.00% exact-match leakage**
- Scenarios: digital arrest, mule funnel, synthetic ID, CNP, ATO, burst

## Contents

- `deliverables/PoC_Report.md` — full PoC report with charts and method
- `deliverables/report.pdf` / `report.tex` — print-ready report
- `deliverables/visuals/` — 11 figures (confusion matrices, PR curves, dry-run audits)
- `deliverables/appendix/` — metrics JSONs, experiment logs, scenario cards
- `Synthetic_Fraud_Framework_Report_v2.pdf` — framework report
- `credit_risk.pdf`, `fraud_detection.pdf` — reference briefs

## Method

5-model generative ensemble (MaskedPredictor + Copula champions) with threshold
engineering on RandomForest (n_estimators=200, max_depth=15), evaluated
TSTR-style: models trained with synthetic augmentation, tested on real held-out
fraud. Every synthetic record is statistically unique — zero PII.

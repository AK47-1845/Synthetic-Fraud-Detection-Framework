# Synthetic Fraud Detection — PoC Deliverables

## Quick Start

**Read this first:** [`PoC_Report.md`](./PoC_Report.md) — the complete, self-contained proof-of-concept report with all results, charts, and analysis.

---

## What's Inside

### Primary Document
| File | Description |
|:---|:---|
| `PoC_Report.md` | **Single-file PoC report** — all sections, all charts embedded, ready to share |

### Visual Assets (`./visuals/`)
11 publication-grade charts covering every result:

| # | Chart | Key Insight |
|:---:|:---|:---|
| 01 | Champion Story | 3-stage model evolution — **+39.1% F1** |
| 02 | Confusion Matrices | Before/after error analysis — 67% fewer false positives |
| 03 | FP Eradication | Full journey from XGBoost → Champion — 89% FP reduction |
| 04 | Plateau Injection Curve | Optimal synthetic volume: 35K–52K records |
| 05 | Generator Leaderboard | MaskedPredictor + Copula lead the ensemble |
| 06 | Fraud Scenario Distribution | 6-scenario injection breakdown |
| 07 | Feature Importance | Velocity + amount drive detection — not identity |
| 08 | PR Trajectory | PR-AUC improvement: 0.492 → 0.579 |
| 09 | Deep Audit | Wasserstein + JS divergence per generator |
| 10 | Threshold Tradeoff | FP reduction at each threshold level |
| 11 | Quality Radar | 12-test battery: Copula vs MaskedPredictor |

### Raw Data Appendix (`./appendix/`)
All source-of-truth data files — every number in the report is traceable here:

| File | Contents |
|:---|:---|
| `model_metrics.json` | Full before/after metrics for all 4 models |
| `before_after_comparison.csv` | Tabular comparison of all model configurations |
| `champion_config.json` | Champion RF configuration and optimal threshold |
| `injection_plateau_results.csv` | F1 and PR-AUC at 12 injection volumes |
| `generator_quality_scores.json` | Genuity quality scores per generator |
| `custom_eval_scores.json` | 12-test custom quality battery results |
| `deep_audit_results.json` | Wasserstein distance + JS divergence per feature |
| `scenario_cards.json` | Full definitions of all 6 fraud scenarios |
| `data_inventory.csv` | Dataset manifest: sources, rows, fraud rates |

---

## Hero Numbers

| Metric | Value |
|:---|---:|
| F1 Uplift (Augmented RF) | **+39.1%** (0.407 → 0.566) |
| Champion F1 | **0.566** |
| Precision (Augmented RF) | **53.9%** |
| PR-AUC Uplift | **+17.6%** (0.492 → 0.579) |
| False Positive Reduction | **↓ 67.2%** (3,338 → 1,094) |
| Champion FP (0.85 threshold) | **361** (↓ 89.2%) |
| Synthetic Records | **58,338** (0% leakage) |
| Generator Champions | **MaskedPredictor + Copula** |
| Fraud Scenarios | **6** (Digital Arrest, Mule, Synth ID, CNP, ATO, Burst) |

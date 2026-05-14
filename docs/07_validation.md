# Limitations & Validation

## Out-of-Time Validation

An independent out-of-time (OOT) validation was performed using 2025 Q1 origination data (45,200 applications) by the Model Validation Unit.

### Performance Metrics

| Metric | Development | OOT (2025 Q1) | Threshold | Status |
| --- | --- | --- | --- | --- |
| AUC-ROC | 0.89 | 0.87 | > 0.80 | Pass |
| Gini | 0.78 | 0.74 | > 0.60 | Pass |
| KS Statistic | 0.52 | 0.48 | > 0.40 | Pass |
| Hosmer-Lemeshow p | 0.42 | 0.31 | > 0.05 | Pass |
| PSI (score dist.) | — | 0.08 | < 0.15 | Pass |

### Gini Coefficient Decay Analysis

| Period | Gini | Decay (pp) | Notes |
| --- | --- | --- | --- |
| Development (2023 H1) | 0.78 | — | Baseline |
| Validation (2023 H2) | 0.76 | -2 | Within tolerance |
| OOT (2024 Full) | 0.75 | -3 | Within tolerance |
| OOT (2025 Q1) | 0.74 | -4 | Monitoring required |

## Known Limitations

1. **Expatriate Segments:** Performance degrades for recently arrived expatriates (< 6 months residency) due to limited credit bureau history.
2. **Self-Employed Applicants:** Income verification is challenging; model relies on declared income which may be unreliable.
3. **Macroeconomic Sensitivity:** The model does not incorporate forward-looking macroeconomic variables.

{{findings:credit_risk}}

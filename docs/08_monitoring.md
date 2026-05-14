# Ongoing Monitoring

## Monitoring Framework

The model is monitored on a **daily** basis using the Population Stability Index (PSI) as the primary drift indicator. Automated alerts are triggered when PSI exceeds the configured threshold.

### Alert Thresholds

| Metric | Green | Amber | Red |
| --- | --- | --- | --- |
| PSI (Score Distribution) | < 0.10 | 0.10–0.15 | > 0.15 |
| PSI (Feature Drift) | < 0.15 | 0.15–0.25 | > 0.25 |
| Approval Rate Shift | < 2pp | 2–5pp | > 5pp |
| Default Rate Shift | < 0.5pp | 0.5–1.0pp | > 1.0pp |

### Escalation Protocol

- **Green:** No action required. Monthly summary report.
- **Amber:** Investigation required within 5 business days. Findings reported to Model Owner.
- **Red:** Immediate escalation to MRC. Model may be suspended pending review.

{{baseline:credit_risk}}

{{monitor:credit_risk}}

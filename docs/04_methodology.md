# Methodology & Assumptions

## Model Architecture

A **Logistic Regression** model was selected for its transparency and interpretability, which are regulatory requirements for Tier 1 credit models under CBUAE guidance.

### Weight of Evidence (WoE) Binning

All continuous variables are discretised into WoE bins to enforce monotonicity. Information Value (IV) is used for feature selection, retaining only variables with IV > 0.1.

### Probability of Default

The probability of default is given by:

$$P(Y=1) = \frac{1}{1 + e^{-(\beta_0 + \beta_1 X_1 + \dots + \beta_n X_n)}}$$

### Feature Selection Results

The following variables were retained after IV screening:

| Variable | IV | WoE Range | Bins |
| --- | --- | --- | --- |
| `debt_ratio` | 0.42 | -0.8 to 1.2 | 5 |
| `bureau_score` | 0.38 | -1.1 to 0.9 | 6 |
| `income` | 0.31 | -0.6 to 0.8 | 4 |
| `credit_history_years` | 0.28 | -0.5 to 0.7 | 4 |
| `payment_regularity` | 0.24 | -0.4 to 0.6 | 3 |
| `dpd_12m` | 0.22 | -0.9 to 0.3 | 4 |
| `utilisation_max` | 0.19 | -0.3 to 0.5 | 3 |
| `monthly_disposable` | 0.15 | -0.2 to 0.4 | 3 |
| `employment_tenure` | 0.12 | -0.3 to 0.3 | 3 |

## Key Assumptions

1. **Stationarity:** The relationship between features and default probability is assumed stable over the training window (2018–2023).
2. **Independence:** Individual loan applications are treated as independent observations.
3. **Monotonicity:** WoE binning enforces monotonic risk ordering within each variable.
4. **Population Stability:** The applicant population composition is assumed to remain broadly consistent with the training period.

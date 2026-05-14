# Overview & Strategy

Binary classifier for retail credit risk assessment. Evaluates individual consumer capacity to repay unsecured personal loans over a 36-month horizon.

## Inputs
- `income`: Annual income (float)
- `debt_ratio`: Debt-to-income ratio (float)
- `credit_history_years`: Years of credit history (int)

## Outputs
- `risk_score`: Probability of default [0, 1]
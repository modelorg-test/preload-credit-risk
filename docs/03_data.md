# Data Set Description

## Training Dataset

The model was trained on **1.2 million** historical retail loan applications from January 2018 to December 2024. The dataset was sourced from the core banking system and enriched with credit bureau records from Al Etihad Credit Bureau (AECB).

### Exclusions

Forbearance periods during the 2020 pandemic (March–December 2020) were excluded to prevent distributional drift caused by government-mandated payment holidays.

### Dataset Composition

| Year | Applications | Default Rate | Notes |
| --- | --- | --- | --- |
| 2018 | 145,230 | 3.2% | Baseline period |
| 2019 | 162,410 | 2.8% | Pre-pandemic |
| 2020 | 98,700 | 1.1% | Partial year (exclusions applied) |
| 2021 | 178,500 | 4.1% | Post-forbearance spike |
| 2022 | 195,200 | 3.6% | Normalisation |
| 2023 | 210,400 | 3.3% | Stable |
| 2024 | 209,560 | 3.0% | Latest training window |

### Feature Summary

The final feature set comprises 23 variables across three categories:

- **Demographic (7):** Age, nationality group, employment sector, tenure, marital status, number of dependents, housing type
- **Financial (9):** Annual income, total debt, debt-to-income ratio, number of active credit lines, maximum credit utilisation, average balance, savings ratio, monthly disposable income, employer category
- **Behavioural (7):** Days past due (last 12M), number of inquiries (last 6M), credit history length, payment regularity score, revolving balance trend, worst delinquency status, bureau score

### Data Split

The dataset was partitioned as follows:

| Split | Records | Period | Purpose |
| --- | --- | --- | --- |
| Training | 840,000 (70%) | 2018–2023 | Model fitting |
| Validation | 180,000 (15%) | 2023 H2 | Hyperparameter tuning |
| Out-of-Time Test | 180,000 (15%) | 2024 | Final performance evaluation |

# Implementation Process

## Deployment Architecture

The credit risk scorecard is deployed as a stateless REST API behind an internal API gateway. Scoring requests are processed synchronously with a p99 latency target of 50ms.

### System Components

| Component | Technology | Purpose |
| --- | --- | --- |
| Scoring API | FastAPI + ONNX Runtime | Real-time inference |
| Feature Store | Redis (online) / Hive (offline) | Feature serving |
| Model Registry | MLflow | Version tracking and artifact storage |
| Orchestrator | Airflow | Batch retraining and validation pipelines |

## Batch Pipeline

Monthly batch scoring is executed for the full portfolio (approx. 1.2M active accounts) to refresh risk ratings and trigger downstream provisioning adjustments.

### Pipeline Steps

1. Feature extraction from core banking system (T-1 day snapshot)
2. WoE transformation using the production binning configuration
3. Score generation via the registered ONNX model artifact
4. Output validation (score distribution PSI check vs. baseline)
5. Publication to the downstream risk data warehouse

## Current Lifecycle

{{stage:credit_risk}}

## Experiment Tracking

{{experiment:credit_risk}}

# 🧠 Neuro-Insight Lakehouse

## Real-World Evidence (RWE) Data Engineering Pipeline for Neurological Telemetry

Neuro-Insight Lakehouse is a 7-day hands-on data engineering project
built using Databricks, PySpark, Delta Lake, Spark SQL, and Databricks
Workflows.

The project simulates neurological telemetry / digital-biomarker-style
data and demonstrates how raw data can be transformed into validated,
analytics-ready datasets using a Medallion Lakehouse architecture.

> **Disclaimer:** This project uses fully synthetic data for educational
> and portfolio purposes. It is not a clinical system and does not
> diagnose or predict neurological disease.

---

## 🎯 Project Objective

The objective of this project is to demonstrate an end-to-end
Lakehouse data engineering pipeline for simulated neurological
telemetry data.

The pipeline demonstrates:

- Synthetic telemetry data generation
- Raw data ingestion
- Delta Lake storage
- Data validation
- Invalid-record quarantine
- Silver-layer transformation
- Gold-layer analytical aggregation
- Data quality monitoring
- Audit logging
- Databricks Workflow orchestration

---

## 🏗️ Architecture

```text
              Synthetic Telemetry
                       │
                       ▼
                ┌─────────────┐
                │    BRONZE   │
                │ Raw Telemetry│
                └──────┬──────┘
                       │
                       ▼
              Data Validation
                       │
             ┌─────────┴─────────┐
             │                   │
             ▼                   ▼
       ┌───────────┐      ┌──────────────┐
       │  SILVER   │      │  QUARANTINE  │
       │ Valid Data│      │ Invalid Data │
       └─────┬─────┘      └──────────────┘
             │
             ▼
       ┌───────────┐
       │   GOLD    │
       │Daily Metrics│
       └─────┬─────┘
             │
             ▼
          Analytics

             +

     Data Quality Monitoring
             │
     Audit Logging
             │
     Workflow Orchestration

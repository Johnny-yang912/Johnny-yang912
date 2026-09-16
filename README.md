# Data Engineering & Backend Engineering Portfolio

[繁體中文版](./README.zh-TW.md)

Focused on data engineering and backend development.
Building production-oriented data pipelines and APIs with Python · SQL · FastAPI · PostgreSQL · Airflow · BigQuery · dbt.

---

## Projects

### 🏗️ E-Commerce Data Ingestion Platform
An end-to-end data pipeline from ingestion to analytics, using e-commerce orders as the domain. Untrusted inbound data is turned into trusted analytical data through layered quality contracts, and every change to a quality judgment stays auditable.

Data flow: POST /orders → Raw → Celery Worker (CAS claim, idempotent write) → ODS + quality_events → Airflow → BigQuery → dbt (stg → int → dim / fct → rpt) → Looker Studio

Verified under high concurrency, duplicate submissions, malformed data, and worker SIGKILL crash recovery. It has 445 unit/integration tests and 93 dbt tests, and 54 ADRs record each decision along with the alternatives that were rejected.

Tech: Python · SQL · FastAPI · PostgreSQL · Celery · Redis · Airflow · BigQuery · dbt · OpenTelemetry
→ [View Project](https://github.com/Johnny-yang912/ecommerce-data-ingestion-platform)

---

### 🔄 Simple ETL Practice
A basic ETL exercise demonstrating local data transformation and loading.

Data flow: Local download → Python transformation → SQLite

Tech: Airflow · Docker · Python · SQLite
→ [View Project](https://github.com/Johnny-yang912/easy_ETL_and_OOP)

---

### 🔍 Credit Card Fraud Detection
End-to-end ML pipeline: baseline → time features → geo features → threshold tuning.
Final model: PR-AUC 0.8477 · F2 0.7642.
Covers full ML workflow from feature engineering to FastAPI deployment.

Tech: Scikit-Learn · Pandas · FastAPI · Python
→ [View Project](https://github.com/Johnny-yang912/CreditCard-TransactionFraud-PredictionModel)

---

### 📊 Telecom Customer Churn Analysis
SQL-based analysis identifying contract terms and service usage as key churn factors,
with Power BI dashboard.

Tech: SQL · Power BI
→ [View Project](https://github.com/Johnny-yang912/data-analysis-portfolio)


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

### 🏭 Manufacturing Report Ingestion Pipeline (.NET)

A rebuild of the E-commerce Data Ingestion Platform's ingestion layer in ASP.NET Core, with the data domain migrated from e-commerce orders to manufacturing work-order reports.

Validates that the ingestion architecture is portable across tech stacks and data domains: keeps the core design of fast landing, CAS claiming, and flag-don't-reject error handling; replaces Celery + Redis with an in-process BackgroundService + Channel, documenting the trade-offs in crash recovery and burst buffering.

Data flow: POST /api/reports → Raw → Channel → ChannelWorker (CAS claim, idempotent write) → ODS; ScanWorker recovers pending and timed-out processing records

Tech: C# · ASP.NET Core · EF Core · SQL Server · BackgroundService → [View project](https://github.com/Johnny-yang912/report-data-pipeline-csharp)

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


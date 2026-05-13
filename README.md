# Data Engineering & Backend Engineering Portfolio

[繁體中文版](./README.zh-TW.md)

Focused on data engineering and backend development.
Building production-oriented data pipelines and APIs with Python · FastAPI · PostgreSQL · SQLAlchemy.

---

## Projects

### 🏗️ E-Commerce Data Ingestion Platform
A production-oriented data ingestion backend simulating real-world e-commerce order flow.

Current data flow:
POST /orders → Raw Table → Background Task → Cleaning & Validation → ODS

Future architecture:
POST /orders → Queue → Worker → Raw Table → Cleaning & Validation → ODS
→ Star Schema (dim / fact) → Aggregation → BI

Load tested across scenarios including high concurrency, worker contention, system crash,
and malformed data — validating pipeline stability, reliability, and data correctness
under various failure modes.

Tech: Python · SQL · FastAPI · PostgreSQL · SQLAlchemy
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


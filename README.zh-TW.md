# 資料工程與後端工程作品集

[English Version](./README.md)

專注於資料工程與後端開發。
以 Python · SQL · FastAPI · PostgreSQL · Airflow · BigQuery · dbt 建構貼近生產環境的資料管道與 API。

---

## 專案

### 🏗️ 電商資料擷取平台
模擬真實電商訂單流程的資料擷取後端，設計貼近生產環境的工程實務。

一條從攝入到分析的資料管線，以電商訂單為場域：不可信的入站資料經過分層品質契約，逐步轉為可信的分析資料，而且每一次品質判斷的演進都可稽核。

資料流：POST /orders → Raw → Celery Worker（CAS 認領、冪等寫入）→ ODS + quality_events → Airflow → BigQuery → dbt（stg → int → dim / fct → rpt）→ Looker Studio

驗證了高併發、重複提交、髒資料與 worker SIGKILL 崩潰恢復等場景；445 個單元／整合測試、93 個 dbt 測試；54 條 ADR 記錄每個決策與被否決的替代方案。

技術：Python · SQL · FastAPI · PostgreSQL · Celery · Redis · Airflow · BigQuery · dbt · OpenTelemetry
→ [查看專案](https://github.com/Johnny-yang912/ecommerce-data-ingestion-platform)

---

### 🏭 製造報工資料擷取管線（.NET 版）

以 ASP.NET Core 重新實作電商資料擷取平台的攝入端，並將資料領域遷移至製造業工單報工。

驗證同一套攝入架構在不同技術棧與資料領域下的可移植性：保留快速落地、CAS 認領、錯誤只標記不拒絕的核心設計；以行程內的 BackgroundService + Channel 取代 Celery + Redis，並記錄兩者在崩潰恢復與突發流量緩衝上的取捨。

資料流：POST /api/reports → Raw → Channel → ChannelWorker（CAS 認領、冪等寫入）→ ODS；ScanWorker 掃描補回 pending 與逾時的 processing

技術：C# · ASP.NET Core · EF Core · SQL Server · BackgroundService → [查看專案](https://github.com/Johnny-yang912/report-data-pipeline-csharp)

---

### 🔄 簡易 ETL 練習
ETL 基礎練習，展示本地資料的轉換與寫入流程。

資料流：本地下載 → Python 轉換 → 輸入 SQLite

技術：Airflow · Docker · Python · SQLite
→ [查看專案](https://github.com/Johnny-yang912/easy_ETL_and_OOP)

---

### 🔍 信用卡交易詐欺偵測
以 Kaggle 模擬資料為基礎，逐步完成 baseline → 時間特徵工程 → 地理特徵工程 → 調參與調整閾值，最終模型達成 PR-AUC：0.8477、F2：0.7642。
專案完整涵蓋 Pipeline 建模、特徵工程設計與 FastAPI 部署，展現從資料前處理到模型應用的完整機器學習流程。

技術：Scikit-Learn · Pandas · FastAPI · Python
→ [查看專案](https://github.com/Johnny-yang912/CreditCard-TransactionFraud-PredictionModel)

---

### 📊 電信客戶流失分析
找出合約與服務使用率為關鍵因子，提出降低流失率策略。

技術：SQL · Power BI
→ [查看專案](https://github.com/Johnny-yang912/data-analysis-portfolio)

# 資料工程與後端工程作品集

[English Version](./README.md)

專注於資料工程與後端開發。
以 Python · FastAPI · PostgreSQL · SQLAlchemy 建構貼近生產環境的資料管道與 API。

---

## 專案

### 🏗️ 電商資料擷取平台
模擬真實電商訂單流程的資料擷取後端，設計貼近生產環境的工程實務。

目前資料流：
POST /orders → Raw Table → Background Task → 清洗驗證 → ODS

未來架構方向：
POST /orders → Queue → Worker → Raw Table → 清洗驗證 → ODS
→ Star Schema（dim / fact）→ 聚合運算 → BI

針對高併發、worker 競爭、系統 crash、資料格式錯誤等場景進行壓測，
驗證 pipeline 在各種故障模式下的穩定性、可靠性與資料正確性。

技術：Python · SQL · FastAPI · PostgreSQL · SQLAlchemy
→ [查看專案](https://github.com/Johnny-yang912/ecommerce-data-ingestion-platform)

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

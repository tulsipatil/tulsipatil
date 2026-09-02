# Tulsi Patil — Project Portfolio

MS Computer Science & Engineering candidate at the University at Buffalo, focused on data engineering and data analytics. Below is an overview of my six core portfolio projects, spanning real-time streaming, batch orchestration, data quality, and business intelligence.

tulsipatil24@gmail.com &nbsp;|&nbsp; [LinkedIn](https://linkedin.com/in/tulsipatil) &nbsp;|&nbsp; [GitHub](https://github.com/tulsipatil)

---

## Projects

### [Real-Time E-Commerce Data Engineering Platform](https://github.com/tulsipatil/Real-Time-E-Commerce-Data-Engineering-Platform)
**Tech:** Kafka, PySpark Structured Streaming, AWS S3, Terraform, Docker, GitHub Actions

A real-time event ingestion platform processing e-commerce clickstream events into windowed aggregates for revenue, conversion rate, and active users.

- Built a **Bronze/Silver/Gold medallion architecture** on S3-compatible object storage, separating raw ingestion, deduplicated/typed events, and business-ready aggregates into distinct, replayable layers
- Validated the end-to-end streaming pipeline with **22,360 events** processed through Kafka and the Bronze/Silver/Gold layers; automated pytest suites verified a 10,000-event test producing **$727K** in revenue, **4,316 users**, and **90 gold-layer metrics**
- Provisioned cloud storage and IAM permissions as code using **Terraform**, containerized the local stack with Docker, and validated configuration via **GitHub Actions CI** on every push

### [E-Commerce BI Dashboard & Profitability Analysis](https://github.com/tulsipatil)
**Tech:** SQL, dbt, BigQuery, Power BI, DAX

An end-to-end profitability dashboard answering a specific merchandising question: which product category is missing its margin target, and what should the business do about it.

- Modeled **1,800** e-commerce order records into a dbt semantic layer (staging → order-line fact table → category performance mart) at Category × Region × Month grain, with automated data-quality tests and a BigQuery-ready warehouse loading script
- Built a **Power BI** dashboard with **DAX** measures, KPI cards, region/year slicers, a margin-target comparison chart, a discount/return driver chart, and a conditional-formatted region-by-category matrix
- Identified Furniture as the only category missing its margin target — **3.8%** actual gross margin against a **28%** target (a **24.2-point gap**) — driven by the highest discount rate (**21.3%**) and return rate (**17.3%**) of any category
- Recommended a 3-point discount reduction targeted at the West and South regions, quantifying an estimated **$11.15K** margin upside, framed as an experiment estimate rather than a guaranteed forecast

### [Stock Data Pipeline with Airflow](https://github.com/tulsipatil/Airflow-Batch-Orchestration)
**Tech:** Apache Airflow, Celery, PostgreSQL, Redis, dbt, Docker, GitHub Actions

A Dockerized, distributed ETL pipeline ingesting and transforming daily stock-market data across 100 trading days.

- Orchestrated a **7-task DAG** across PostgreSQL, Redis, Airflow Webserver, Scheduler, Worker, and dbt services, with retries and task dependencies
- Ingested and transformed stock-market data totaling **8.48B market-volume units** into PostgreSQL raw and analytics schemas; built dbt staging, dimension, fact, and aggregate models
- Implemented **idempotent PostgreSQL loading** keyed on `(stock_symbol, trade_date)`, achieving **0 duplicate business keys** and supporting safe reruns and historical backfills
- Achieved **21/22 dbt data-quality tests passing**, validating missing, invalid, negative, freshness, and fact-table integrity conditions

### [NYC Taxi Trip Analysis](https://github.com/tulsipatil/nyc-taxi-analysis)
**Tech:** PySpark, SQL, Hadoop, Pandas, Matplotlib, Seaborn

Large-scale analysis of NYC taxi trip records to uncover trends in fare, tipping, and payment behavior.

- Analyzed **3M+** trip records, identifying **4–7 PM** as the peak demand window and credit cards as the dominant payment method (**70%+** of transactions)
- Used PySpark and SQL-based transformations to clean, aggregate, and analyze large-scale trip data across millions of records
- Found trip characteristics explained only **46%** of tipping variation, highlighting the influence of external customer factors
- Discovered that over **80%** of trips were shorter than **3 miles**, revealing short-distance travel as the dominant demand pattern

### [Data Pipeline Observability & Data Quality Framework](https://github.com/tulsipatil/Data-Observability)
**Tech:** Python, dbt, DuckDB, OpenAI API, Slack, Docker

A Python observability framework monitoring warehouse pipelines for data quality issues before they reach downstream consumers.

- Monitors **6 data quality signals**: null values, duplicate keys, referential integrity, schema-contract drift, data freshness, and row-count volume anomalies against historical run baselines
- Designed to **fail explicitly** when alerting services are unavailable, preventing data-quality failures from silently degrading to a local log
- Integrated the **OpenAI API** to generate plain-language incident summaries (impact, likely cause, next action) delivered automatically through Slack
- Validated with automated pytest coverage and a broken-data test scenario that correctly detected all **5 injected failure types**, confirming the fail-explicit alerting behavior end-to-end

### [Lung Disease Analysis Using Chest X-Ray Data](https://github.com/tulsipatil/LungsDiseaseDetection)
**Tech:** Python, Pandas, OpenCV, Matplotlib, Seaborn, Scikit-learn

Analysis of pediatric chest X-ray images to identify disease-related patterns and support diagnostic decision-making.

- Analyzed **5,863** pediatric chest X-ray images across pneumonia and normal classes
- Identified class imbalance as a key issue, quantifying a **10+ percentage point** performance gap attributable to preprocessing and feature engineering decisions
- Conducted comparative evaluation across **5** predictive approaches, achieving **97.70%** accuracy — outperforming the strongest pretrained model by more than **10 percentage points**
- Developed Grad-CAM visualizations to verify predictions were based on clinically relevant regions rather than imaging artifacts, improving interpretability and stakeholder trust

---

## Publication

**[Early CKD Detection Using Machine Learning](https://github.com/tulsipatil/Chronic_Kidney_Disease_Prediction_Jupyter_Notebook)** — *Springer LNEE, Vol. 1297, 2025*
Analyzed 24 clinical variables and applied feature selection to identify the 10 most influential indicators for Chronic Kidney Disease, reducing feature dimensionality by 58% while achieving 96.25% diagnostic accuracy across 6 predictive approaches.

---


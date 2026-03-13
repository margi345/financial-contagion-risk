# 🏦 Systemic Financial Contagion Risk Monitor

> Predicting which banks will trigger a domino collapse using Graph ML and Databricks

## 🎯 Problem Statement
In 2008, Lehman Brothers' collapse triggered a $10 trillion global crisis due to interconnected financial institutions. This project builds an end-to-end ML system to identify systemically dangerous banks before they fail.

## 🏗️ Architecture
Bronze (Raw Data) → Silver (Features + Network) → Gold (ML Predictions)

## 📊 Dataset
- FDIC Bank Financials (10,000 rows)
- FDIC Failed Banks (4,114 rows)
- FDIC Institutions (10,000 rows)
- FDIC Summary (7,989 rows)

## 🔧 Tech Stack
- Databricks Community Edition
- PySpark & Delta Lake
- NetworkX (Graph Analysis)
- Random Forest (ML Model)
- MLflow (Experiment Tracking)

## 📁 Project Structure
```
financial-contagion-risk/
├── notebooks/
│   ├── 01_bronze_ingestion.ipynb
│   ├── 02_silver_network_building.ipynb
│   ├── 03_gold_feature_engineering.ipynb
│   ├── 04_ml_training.ipynb
│   ├── 05_inference_pipeline.ipynb
│   ├── 06_analytics_dashboard.ipynb
│   └── 07_delta_optimization.ipynb
```

## 🤖 ML Results
- Accuracy  : 95.83%
- Precision : 96.35%
- Recall    : 95.83%
- F1 Score  : 95.91%
- AUC-ROC   : 1.0

## 🔑 Key Insights
- 7 CRITICAL risk banks identified
- Graph features like clustering coefficient ranked in top 4 most important features
- Profit margin is the strongest predictor of bank failure

 ## ⚙️ How To Run
1. Open Databricks Community Edition
2. Import notebooks from `notebooks/` folder
3. Run notebooks in order from 01 to 07
4. Check results in gold_db Delta tables

  ### Current Limitations
- Small dataset of 108 unique banks due to API limit
- AUC of 1.0 suggests possible overfitting on small data
- Oversampling used to handle class imbalance may not generalize well
- Network edges built using deposit similarity proxy instead of real inter-bank exposure data

### Future Improvements
- Use complete FDIC dataset of 4000+ banks for more reliable results
- Integrate real inter-bank exposure data from Federal Reserve for accurate network edges
- Implement Graph Neural Networks (GNN) for deeper network-based predictions
- Add real-time streaming pipeline using Databricks Structured Streaming
- Deploy model as REST API for real-time bank risk scoring
- Add SHAP explainability to explain individual bank risk scores

### Why Results Look Strong
Our high accuracy is expected given the small balanced dataset.
In production with complete data, we would expect:
- AUC-ROC: 0.75 - 0.85
- Accuracy: 80 - 88%
- More reliable precision/recall tradeoff

## 👤 Author

- GitHub: [@margi345](https://github.com/margi345)
- Challenge: Databricks x Codebasics x Indian Data Club




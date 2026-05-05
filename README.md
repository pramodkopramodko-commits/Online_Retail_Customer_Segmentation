# Online Retail Customer Segmentation — End-to-End ML Project

A complete customer intelligence pipeline that segments 4,372 customers from 541,000+ transactions using RFM analysis, KMeans clustering, and ML classifiers — with per-country revenue forecasting.

---

# Project Overview

This project analyses an online retail dataset spanning 13 months and 38 countries to build a production-ready customer segmentation system. It combines time series revenue forecasting with RFM-based clustering and machine learning classification to deliver actionable CRM insights.

---

# What This Project Does

- Cleans and validates 541K+ raw transactions — removes cancellations, null IDs, and invalid rows
- Profiles all **38 countries** into High / Mid / Low revenue tiers
- Builds **per-country ARIMA and SARIMA** models with 12-month ahead forecasts and 95% confidence intervals
- Engineers **RFM features** (Recency, Frequency, Monetary) with IQR outlier capping
- Uses **KMeans clustering** (elbow + silhouette analysis) to find 4 optimal customer segments
- Trains and compares **4 ML classifiers** to predict customer segments on new data
- Exports a **production-ready pipeline** (.pkl) and segment results (CSV/JSON)

---

# Customer Segments Discovered

| Segment | Description | Priority Action |
|---|---|---|
|  Champions (~25%) | Recent, frequent, high-spend. Avg spend: £8,500 | VIP retention & upsell |
|  Loyal Customers (~25%) | Regular buyers, moderate spend. Avg 20 orders | Loyalty rewards program |
|  At-Risk (~25%) | High past spend but 90+ days inactive | Win-back campaigns |
|  New / Occasional (~25%) | Low frequency, 1–3 orders total | Onboarding nurture flows |

---

# Models Used

### ML Classifiers

| Model | F1 Score |
|---|---|
| Logistic Regression | 0.82 |
| Decision Tree | 0.94 |
| Gradient Boosting | 0.95 |
| **Random Forest  Best** | **0.96** |

### Clustering
- **KMeans (k=4)** — validated via elbow method + silhouette score (> 0.45)

### Time Series
- **ARIMA** — AIC grid search per country
- **SARIMA(1,1,1)(1,D,0,12)** — monthly seasonality, 12-month forecast per country

---

# Key Results

- **RF Accuracy ~96%** on segment classification
- **4 interpretable customer segments** from 4,372 customers
- **12-month SARIMA forecast** per focus country
- **+40% revenue spike** identified in Nov–Dec holiday period
- **85%+ revenue** concentrated in UK — international opportunities uncovered

---

# Tech Stack

- **Language:** Python 3.10+
- **Data:** Pandas, NumPy, StandardScaler, LabelEncoder
- **Time Series:** Statsmodels (ARIMA, SARIMA), ADF test
- **Clustering:** Scikit-learn KMeans, Silhouette Score
- **ML:** Scikit-learn (Random Forest, GBM, Decision Tree, Logistic Regression, GridSearchCV)
- **Visualisation:** Matplotlib, Seaborn, PCA 2D plots
- **Export:** Joblib (.pkl), JSON, CSV

---

# Files

| File | Description |
|---|---|
| `P2_OnlineRetail_Segmentation.ipynb` | Full notebook — EDA, RFM, clustering, ML |
| `Online_Retail_Report.docx` | Written project report |

---

# Dataset

- **Source:** UCI Machine Learning Repository / Kaggle
- **File:** `OnlineRetail.csv`
- **Size:** 541,909 rows × 8 features → 397,000 after cleaning
- **Countries:** 38 unique countries
- **Period:** December 2010 – December 2011

---

# Author

**Pramod K O**  
[LinkedIn Profile URL:linkedin.com/in/pramod-k-o-775b31306 ] 

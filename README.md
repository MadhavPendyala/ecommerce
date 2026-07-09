# E-Commerce Customer Segmentation & Recommendation Engine

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Scikit-Learn](https://img.shields.io/badge/scikit--learn-1.0%2B-orange)
![Machine Learning](https://img.shields.io/badge/ML-Unsupervised%20Learning-green)

An end-to-end Machine Learning solution that leverages **Unsupervised Learning** (**K-Means Clustering** & **Principal Component Analysis - PCA**) to group e-commerce customers based on purchasing behavior (Recency, Frequency, Monetary Value, Average Order Value) into distinct profiles: **Premium**, **Occasional**, and **Budget** shoppers.

---

##  Project Overview & Scenario

Modern e-commerce platforms like Amazon handle millions of active buyers daily. Blanket marketing strategies result in high promotional spend with low conversion rates. This project automates customer behavioral profiling to enable targeted discounting strategies, loyalty engagement, and personalized product recommendations.

### Key Objectives
* **Behavioral Feature Engineering:** Process transaction attributes (Total Spend, Order Frequency, Average Order Value, Recency Days).
* **Optimal Clustering:** Determine optimal cluster count ($K$) using the **Elbow Method** (WCSS) and **Silhouette Score Analysis**.
* **Dimensionality Reduction:** Compress 4D customer feature space into 2D using **PCA** while retaining over 80% total variance for clear visualization.
* **Strategic Playbook:** Map each customer segment to targeted business actions and recommendation strategies.

---

##  Project Architecture

├── data/                       # Dataset directory (raw & processed)
├── notebooks/                  # Jupyter Notebooks containing execution steps
│   └── Customer_Segmentation.ipynb
├── reports/                    # Generated PDF reports and visualizations
│   ├── Elbow_Plot.png
│   └── PCA_Clusters.png
├── src/                        # Source code for pipeline
│   ├── preprocessing.py        # Feature scaling using StandardScaler
│   ├── clustering.py           # K-Means model training & optimal K logic
│   └── visualization.py        # PCA transformation & plotting functions
├── README.md                   # Repository summary & documentation
└── requirements.txt            # Python dependencies

Methodology & Key Results

### 1. Optimal Cluster Determination
Using the **Elbow Method** and **Silhouette Coefficients**, $K = 3$ was identified as the mathematical sweet spot balancing cluster cohesion and separation.

### 2. PCA Variance Retention
* **Principal Component 1 (PC1):** Captures **62.4%** of variance (Spend & Frequency).
* **Principal Component 2 (PC2):** Captures **21.8%** of variance (Recency & Order Value).
* **Cumulative Variance Preserved:** **84.2%**

### 3. Customer Segment Profiling

| Segment Name | Avg Spend ($) | Avg Frequency | Avg Order Value ($) | Recency (Days) | Actionable Strategy |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Budget Shoppers** | ~$812 | ~5 orders | ~$168 | ~118 days | Flash sales, discount vouchers, free shipping thresholds |
| **Occasional Shoppers** | ~$3,015 | ~18 orders | ~$169 | ~37 days | Targeted category discounts, loyalty program nudges |
| **Premium Shoppers** | ~$8,480 | ~45 orders | ~$192 | ~7 days | VIP perks, early product access, luxury cross-sells |


# CryptoClustering

This assignment applies **K-Means clustering** to analyze and group cryptocurrencies based on their price changes over different time periods. Additionally, **Principal Component Analysis (PCA)** is used to reduce dimensionality and optimize clustering performance.

---

## Project Overview
### **Objective**
- Identify if cryptocurrencies can be clustered based on **24-hour** and **7-day price changes**.
- Use **K-Means Clustering** and **PCA** to optimize and analyze data patterns.
- Compare clustering results before and after PCA.

### **Techniques Used**
- **K-Means Clustering** (to group cryptocurrencies)
- **Elbow Method** (to determine the optimal number of clusters)
- **Principal Component Analysis (PCA)** (to reduce dimensionality)
- **hvPlot** (for interactive data visualization)

### **Dataset**
- **File:** `crypto_market_data.csv`
- **Content:** Contains price change percentages of various cryptocurrencies across different timeframes.

---

## Key Steps & Methodology

### **1?? Data Preprocessing**
- Loaded the cryptocurrency dataset into a Pandas **DataFrame**.
- **Standardized** numerical features using `StandardScaler()` for better clustering performance.

### **2?? Finding the Best k Using the Elbow Method**
- Applied **K-Means clustering** to the **scaled dataset**.
- Computed **inertia values** for **k = 1 to 11**.
- **Visualized the Elbow Curve** using `hvPlot` to determine the optimal `k`.

### **3?? Clustering Cryptocurrencies (Original Data)**
- Fit **K-Means** using the best `k` value.
- **Assigned cluster labels** to each cryptocurrency.
- **Created a scatter plot** (24h % vs. 7d %) to visualize clusters.

### **4?? Applying PCA for Dimensionality Reduction**
- Reduced the dataset to **three principal components (PC1, PC2, PC3)**.
- **Computed explained variance** to ensure minimal information loss.

### **5?? Finding the Best k Using PCA Data**
- Applied the **Elbow Method again** on the **PCA-transformed data**.
- **Compared clustering results** before and after PCA.

### **6?? Clustering Cryptocurrencies (PCA Data)**
- Fit **K-Means** on **PCA-transformed** features.
- **Visualized clusters** using PC1 vs. PC2.

### **7?? Comparing Results**
- **Compared Elbow Curves** (Original vs PCA) to see if `k` changed.
- **Compared Clustering Results** (Original vs PCA) to analyze the impact of using fewer features.

---

## Key Findings
? **Best k-value found:** **4** (same for original and PCA data).  
? **PCA reduced dimensions while preserving ~89.5% variance**.  
? **Clusters remained consistent before and after PCA** (demonstrating PCA's effectiveness).  
? **Elbow Curve and cluster visualization confirmed meaningful groupings of cryptocurrencies**.

---

## Installation & Setup

### **1?? Install Required Libraries**
Ensure you have the necessary Python packages installed:
```bash
pip install pandas scikit-learn hvplot matplotlib
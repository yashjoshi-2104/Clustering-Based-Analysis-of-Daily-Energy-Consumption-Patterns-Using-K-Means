# Clustering-Based-Analysis-of-Daily-Energy-Consumption-Patterns-Using-K-Means
Applied K-Means clustering to time-series electricity data to identify five distinct daily energy consumption patterns using normalized half-hourly load profiles.

##  Project Overview

This project applies **unsupervised machine learning** techniques to analyze and identify daily energy consumption patterns from time-series electricity load data. By transforming hourly energy readings into normalized half-hourly daily profiles and applying K-Means clustering, the project uncovers distinct consumption behaviors across different days.

The goal is to demonstrate how clustering techniques can reveal meaningful patterns in energy demand data to support data-driven decision-making.

---

##  Objectives

* Load and preprocess time-series energy consumption data
* Convert hourly readings to half-hourly intervals
* Aggregate daily energy load profiles (48 time slots per day)
* Normalize data for clustering
* Apply K-Means clustering (4–6 clusters)
* Visualize cluster centroids
* Evaluate clustering quality using Silhouette Score

---

##  Dataset

The dataset used in this project comes from:

**PJM Interconnection (PJM Hourly Energy Consumption Dataset)**

* Regional electricity load data
* Hourly time-series energy readings
* Multiple years of historical demand data
* Unit: Megawatts (MW)

For this project, the `PJME_hourly.csv` regional dataset was used.

---

##  Technologies Used

* Python
* pandas
* NumPy
* scikit-learn
* matplotlib

---

## Methodology

### 1️) Data Preprocessing

* Loaded CSV data into pandas
* Converted `Datetime` column to proper datetime format
* Sorted data chronologically
* Removed duplicate timestamps
* Resampled hourly data to **30-minute intervals**
* Interpolated missing values

---

### 2️) Daily Profile Construction

* Extracted date from timestamp
* Created 48 half-hour time slots (0–47)
* Aggregated data into daily load profiles using pivot tables
* Each row represents one day
* Each column represents one half-hour interval

---

### 3️) Data Normalization

To ensure fair clustering:

* Applied `StandardScaler`
* Removed scale differences between days
* Standardized consumption values

---

### 4️) K-Means Clustering

* Applied K-Means algorithm
* Selected **5 clusters** (within required 4–6 range)
* Assigned each day to a cluster
* Extracted cluster centroids

---

### 5️) Cluster Evaluation

* Used **Silhouette Score**
* Achieved score ≈ **0.33**
* Indicates moderate but meaningful separation (expected for real-world time-series energy data)

---

### 6️) Visualization

* Plotted cluster centroids as line graphs
* X-axis → Half-hour time slots (0–47)
* Y-axis → Normalized energy consumption
* Saved output as PNG file

---

##  Results & Insights

The clustering process identified **five distinct daily energy consumption patterns**, including:

* High peak demand days
* Stable consumption days
* Morning-dominant usage patterns
* Evening-dominant load behavior
* Lower overall demand days

These patterns reflect natural variations in electricity demand influenced by behavioral, seasonal, and operational factors.

The visualization of centroids clearly shows differences in peak timing and load intensity across clusters.

---

##  Why K-Means?

K-Means is:

* Efficient for large datasets
* Effective for pattern segmentation
* Suitable for time-series profile clustering
* Interpretable via centroid visualization

---

##  Key Learnings

* Time-series data requires careful preprocessing
* Normalization significantly impacts clustering performance
* Real-world energy data rarely produces very high silhouette scores
* Unsupervised learning is powerful for discovering hidden structure

---

##  Project Structure

```
├── Energy Consumption Pattern Clustering.ipynb
├── PJME_hourly.csv
├── cluster_centroids.png
└── README.md
```

---

## Conclusion

This project successfully demonstrates how unsupervised machine learning techniques can be applied to time-series energy data to discover meaningful daily consumption patterns. The clustering-based approach provides valuable insights into demand behavior and showcases the practical application of K-Means in energy analytics.


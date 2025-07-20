#  Customer Segmentation using K-Means Clustering

This project applies unsupervised machine learning to identify distinct customer groups based on their **Annual Income** and **Spending Score**, helping businesses better understand customer behavior and tailor strategies accordingly.

---

## Project Overview

Customer segmentation is the practice of dividing a company's customers into groups that reflect similarity among customers in each group. This project clusters mall customers using **K-Means Clustering**, a popular unsupervised learning algorithm.

The dataset used is `Mall_Customers.csv`, and the features selected for clustering are:
- **Annual Income (k$)**
- **Spending Score (1–100)**

---

##  Technologies Used

| Tool/Library         | Purpose                        |
|----------------------|--------------------------------|
| Python               | Programming Language           |
| Pandas & NumPy       | Data manipulation              |
| Matplotlib & Seaborn | Data visualization             |
| Scikit-learn         | KMeans clustering algorithm    |

---

##  Dataset Information

- **Total Samples**: 200
- **Features**:
  - `CustomerID`
  - `Gender`
  - `Age`
  - `Annual Income (k$)`
  - `Spending Score (1–100)`

There are no missing values in the dataset.

---

## 🧪 Methodology

### Step 1: Data Selection
```python
X = data.iloc[:, [3, 4]].values  # Selecting Annual Income & Spending Score
```

### Step 2: Elbow Method to Find Optimal Clusters
```python
for i in range(1, 11):
    kmeans = KMeans(n_clusters=i, init='k-means++', random_state=42)
    kmeans.fit(X)
    wcss.append(kmeans.inertia_)
```
- Optimal number of clusters determined to be **5**.

### Step 3: Model Training
```python
kmeans = KMeans(n_clusters=5, init='k-means++', random_state=0)
Y = kmeans.fit_predict(X)
```

---

##  Cluster Visualization

Each customer is grouped into one of the 5 clusters using different colors:
- Green: Cluster 1
- Red: Cluster 2
- Yellow: Cluster 3
- Violet: Cluster 4
- Blue: Cluster 5

Cluster centroids are also displayed for better interpretability.

---

##  Results

- Clusters reveal different types of customers:
  - High Income, Low Spending
  - Low Income, High Spending
  - Balanced Spend vs Income
  - ...and more


---

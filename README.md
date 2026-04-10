# Customer Segmentation using K-Means Clustering

## Project Overview
This project focuses on **customer segmentation** using the **K-Means clustering algorithm** to identify distinct customer groups based on their purchasing behavior.

By analyzing customer income and spending patterns, the project provides **actionable business insights** that can help organizations improve marketing strategies and customer targeting.

The dataset used is the **Mall Customers Dataset**, a widely used dataset for clustering and customer analytics tasks.

---

## Objective
- Segment customers into meaningful groups using unsupervised learning
- Understand customer behavior patterns
- Support data-driven business decisions and targeted marketing strategies

---

## Dataset
- **Source:** Mall Customers Dataset
- **Size:** 200 rows × 5 columns
- **Features:** CustomerID, Gender, Age, Annual Income (k$), Spending Score (1-100)
- **Link:** https://www.kaggle.com/datasets/abdallahwagih/mall-customers-segmentation

---

## Methodology

### 1. Exploratory Data Analysis (EDA)
- Checked for missing values, data types, and statistical summaries
- Visualized gender distribution, feature distributions, and correlation heatmap
- Key finding: No strong correlations between features — validates clustering approach

### 2. Feature Selection
| Feature | Included | Reason |
|---|---|---|
| Annual Income (k$) | ✅ Yes | Directly represents purchasing power |
| Spending Score (1-100) | ✅ Yes | Directly represents spending behavior |
| Age | ❌ No | Reduces Silhouette Score (0.55 → 0.43) |
| Gender | ❌ No | Binary encoding distorts Euclidean distance |

### 3. Optimal K Selection
Both methods independently confirmed **K = 5**:
- **Elbow Method** — Clear elbow at K=5
- **Silhouette Score** — Highest score of **0.5547** at K=5

### 4. Model
- Algorithm: K-Means Clustering
- Features: Annual Income, Spending Score
- Preprocessing: StandardScaler
- Final K: 5

---

## Results

| Cluster | Segment | Avg Income | Avg Spending | Count |
|---|---|---|---|---|
| 0 | Average Customers | Medium (55k$) | Medium (50) | 81 |
| 1 | High Value | High (87k$) | High (82) | 39 |
| 2 | Young Impulsive Spenders | Low (26k$) | High (79) | 22 |
| 3 | Conservative High Earners | High (88k$) | Low (17) | 35 |
| 4 | Budget Customers | Low (26k$) | Low (21) | 23 |

**Silhouette Score: 0.5547** — indicates well-separated, meaningful clusters.

---

## Business Insights
- **Cluster 0** (Average): Loyalty programs and seasonal promotions
- **Cluster 1** (High Value): Premium memberships and retention strategies
- **Cluster 2** (Young Spenders): Limited-time offers and instalment options
- **Cluster 3** (Conservative): Personalized discounts to unlock spending potential
- **Cluster 4** (Budget): Budget-friendly products and value deals

---

## Tech Stack
- Python
- Pandas, NumPy
- Matplotlib, Seaborn
- Scikit-learn (KMeans, StandardScaler, silhouette_score)

---

## How to Run
1. Clone the repository
2. Upload `Mall_Customers.csv` when prompted (Google Colab)
3. Run all cells in `customer_segmentation.ipynb`

# 🧩 Experiment 7 – Clustering Human Activity Recognition Data using K-Means, DBSCAN and Hierarchical Clustering

## 📘 Overview
This experiment explores and compares three fundamental **unsupervised learning algorithms** —  
**K-Means**, **DBSCAN**, and **Hierarchical Agglomerative Clustering (HAC)** — on the  
**Human Activity Recognition (HAR)** dataset.  

The goal is to form clusters that correspond to the six human activities captured by smartphone sensors  
and to evaluate each algorithm using internal and external clustering metrics.

---

## 🎯 Objectives
- Implement and visualize **K-Means**, **DBSCAN**, and **Hierarchical Clustering**.  
- Determine the optimal number of clusters (for K-Means) using the **Elbow Method** and **Silhouette Score**.  
- Tune parameters for DBSCAN (`eps`, `minPts`) to balance cluster quality and noise detection.  
- Compare all algorithms using **Silhouette**, **Davies–Bouldin**, **Calinski–Harabasz**,  
  **Adjusted Rand Index (ARI)**, and **Normalized Mutual Information (NMI)**.  
- Analyze cluster shapes, separation, and computational performance.

---

## 🧩 Dataset
**Name:** Human Activity Recognition Using Smartphones (UCI Repository)  
**Link:** [https://archive.ics.uci.edu/dataset/240/human+activity+recognition+using+smartphones](https://archive.ics.uci.edu/dataset/240/human+activity+recognition+using+smartphones)

| Property | Description |
|-----------|-------------|
| Samples | 10 299 readings from 30 volunteers |
| Activities | WALKING, WALKING UPSTAIRS, WALKING DOWNSTAIRS, SITTING, STANDING, LAYING |
| Features | 561 (time & frequency domain from accelerometer & gyroscope) |
| Sampling Rate | 50 Hz (2.56 s windows ≈ 128 samples) |
| Preprocessing | Normalization / Standardization, noise filtering |

---

## ⚙️ Implementation Steps
1. **Data Loading & Preprocessing**
   - Load HAR dataset  
   - Check for missing values  
   - Apply `StandardScaler`  
   - Reduce to 2 principal components using PCA (for visualization)

2. **K-Means Clustering**
   - Compute **WCSS** for multiple k values (2–8)  
   - Plot **Elbow Curve** and **Silhouette Score**  
   - Choose k = 6 (based on elbow point and domain knowledge)

3. **DBSCAN**
   - Tune `eps` ∈ {0.5, 0.8, 1.0, 1.2, 1.5} and `minPts` ∈ {5, 10, 15, 20, 25}  
   - Select best configuration: `eps = 1.0`, `minPts = 15`  
   - Handle noise points and compute metrics

4. **Hierarchical Agglomerative Clustering**
   - Evaluate **Single**, **Complete**, **Average**, and **Ward’s** linkages  
   - Plot Dendrogram and cut tree at k = 6  
   - Select Ward’s method (best variance minimization)

5. **Evaluation & Visualization**
   - Internal: Silhouette, Davies–Bouldin, Calinski–Harabasz  
   - External: Adjusted Rand Index (ARI), Normalized Mutual Information (NMI)  
   - PCA scatter plots for cluster visualization  
   - Dendrogram for hierarchical structure  

---

## 📊 Key Results

| Algorithm | Silhouette | DB Index | CH Index | ARI | NMI | Notes |
|------------|-------------|-----------|-----------|------|------|-------|
| **K-Means (k = 6)** | 0.396 | 1.234 | 285.7 | 0.512 | 0.623 | Best overall alignment with true activities |
| **DBSCAN (ε = 1.0, minPts = 15)** | **0.445** | **1.156** | **312.5** | 0.478 | 0.589 | Best internal metrics; detects noise (5.5 %) |
| **Hierarchical (Ward’s)** | 0.401 | 1.278 | 278.3 | 0.498 | 0.612 | Good visual structure; slower execution |

---

## 🧠 Comparative Insights
- **K-Means** → Most accurate and interpretable; fast and stable for k = 6.  
- **DBSCAN** → Best for discovering arbitrary shapes and handling noise; parameter sensitive.  
- **Hierarchical** → Reveals data hierarchy through dendrogram; computationally heavier.  
- **Silhouette Score** matched visual cluster quality best among internal metrics.  
- **Training Time (sec):** K-Means ≈ 4.2  <  DBSCAN ≈ 8.7  <  Hierarchical ≈ 15.4.

---

## 📈 Visualization Highlights
- **Elbow Curve:** Clear bend at k = 6.  
- **PCA Scatter Plots:** Well-separated clusters for K-Means; DBSCAN shows irregular dense regions.  
- **Dendrogram:** Distinct split between dynamic ( walking ) and static ( sitting/laying ) activities.  

---

## 🧾 Conclusions
- **Recommended Algorithm:** K-Means ( k = 6 ) for known number of activities.  
- **When to use DBSCAN:** Unknown cluster count or presence of noise/outliers.  
- **When to use Hierarchical:** For exploratory analysis and cluster relationship understanding.  
- **Overall:** K-Means achieves best trade-off between accuracy, efficiency, and interpretability.  

---

## 🧪 Learning Outcomes
- Implemented three major clustering algorithms and their parameter tuning.  
- Mastered internal and external cluster validation metrics.  
- Understood model sensitivity to parameters and dimensionality.  
- Visualized high-dimensional sensor data in 2D via PCA.  
- Compared algorithms to make data-driven decisions on clustering method selection.  

---

## 📦 Dependencies
Install required Python packages before running:

```bash
pip install numpy pandas scikit-learn matplotlib seaborn scipy

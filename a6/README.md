# 🧠 Experiment 6 – Dimensionality Reduction and Model Evaluation (With and Without PCA)

## 📘 Overview
This experiment evaluates the effect of **Principal Component Analysis (PCA)** on the performance of various machine-learning classifiers.  
Both **original** (no PCA) and **reduced** (with PCA) feature spaces are tested to analyze the trade-offs between model accuracy, computational efficiency, and stability.

---

## 🎯 Objectives
- Study how **dimensionality reduction** affects model performance.  
- Train and validate models **without PCA** and **with PCA**.  
- Perform **hyperparameter tuning** and **5-fold cross-validation** for both cases.  
- Compare accuracy, F1-score, and training time to understand the impact of PCA.  

---

## 🧩 Datasets

### Dataset 1 – Email Spam/Ham Classification
| Property | Description |
|-----------|-------------|
| Source | Experiment 2 – Email Classification |
| Samples | 5,172 emails |
| Features | 5,000 (TF-IDF features from text) |
| Target Classes | Spam (1), Ham (0) |
| Distribution | Balanced |
| Preprocessing | TF-IDF vectorization + standardization |

### Dataset 2 – Wisconsin Breast Cancer
| Property | Description |
|-----------|-------------|
| Source | Experiment 3 – Ensemble Classification |
| Samples | 569  |
| Features | 30 (medical measurements) |
| Target Classes | Malignant (1), Benign (0) |
| Distribution | 357 Benign, 212 Malignant |
| Preprocessing | Standardization, no missing values |

---

## ⚙️ PCA Configuration
| Dataset | Target Variance | Final Components | Explained Variance % | Justification |
|----------|----------------|------------------|----------------------|----------------|
| Email Spam | 95 % | 42 | 95.2 % | Large dimensionality reduction (5000 → 1184) while preserving information |
| Breast Cancer | 95 % | 10 | 95.1 % | Moderate reduction (30 → 10) for efficiency |

---

## 🤖 Models and Hyperparameter Tuning
Ten models were evaluated both with and without PCA:

| Category | Models | Key Tuned Parameters |
|-----------|---------|---------------------|
| Linear | SVM, Logistic Regression | C, kernel, solver |
| Probabilistic | Naïve Bayes | var_smoothing |
| Instance-based | KNN | k, weights |
| Tree-based | Decision Tree | criterion |
| Ensemble | Random Forest, AdaBoost, Gradient Boost, XGBoost, Stacking | n_estimators, base learners |

---

## 📊 Results Summary

### Key Observations
- **Linear models (SVM, Logistic Regression)** retained accuracy (with only 1–3 % drop) and achieved **25–40 % faster training**.  
- **Tree-based and ensemble models** suffered larger accuracy drops (3–7 %) since PCA disrupts feature interactions.  
- **KNN** achieved balanced trade-offs (≈ 3 % drop, 20 % faster).  
- PCA **reduced variance across folds by 40–60 %**, leading to more stable CV results.  

### Cross-Validation Highlights
- **Email Dataset**: Random Forest (No PCA) ≈ 99.7 %, With PCA ≈ 96 %.  
- **Cancer Dataset**: SVM (No PCA) ≈ 97 %, With PCA ≈ 95 %.  
- PCA most beneficial for high-dimensional text data (Email dataset).  

---

## 🧠 Analysis and Interpretation
| Aspect | Findings |
|---------|-----------|
| Model Stability | Standard deviation reduced 40–60 % with PCA |
| Overfitting | Reduced notably for high-dimensional data |
| Best Performers with PCA | Linear Models (SVM, Logistic Regression) |
| Worst Performers with PCA | Tree and Ensemble Models |
| Training Time | Linear and KNN models trained 25–40 % faster |

---

## 🧩 Dataset-Specific Insights
**Email Spam (Higher Dimensionality)**
- PCA gave major computational benefits (30–40 % faster).  
- Linear models best suited; minimal accuracy loss.  

**Breast Cancer (Medium Dimensionality)**
- Moderate efficiency gains (≈ 25 %).  
- Accuracy impact minimal; PCA recommended for faster execution.  

---

## 🧾 Conclusions
- ✅ **Use PCA** for:
  - Linear models (SVM, Logistic Regression)  
  - High-dimensional data (≥ 1000 features)  
  - When speed and stability are priorities  

- 🚫 **Avoid PCA** for:
  - Tree-based or ensemble methods  
  - Low-dimensional datasets (< 50 features)  
  - When maximum accuracy or feature interpretability is crucial  

- 📈 Overall: PCA provides excellent efficiency–accuracy trade-offs for linear models on high-dimensional data.  

---

## 🧪 Learning Outcomes
- Implemented and evaluated PCA on real-world datasets.  
- Analyzed impact on 10+ machine learning models.  
- Understood model–feature space interactions.  
- Mastered hyperparameter tuning in both original and reduced spaces.  
- Developed skills for balancing accuracy and efficiency in model selection.  

---

## 📦 Dependencies
Install the required packages:

```bash
pip install numpy pandas scikit-learn matplotlib seaborn xgboost

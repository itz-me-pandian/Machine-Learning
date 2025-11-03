# 🧠 Experiment 5 – Perceptron vs Multilayer Perceptron (A/B Experiment) with Hyperparameter Tuning

## 📘 Overview
This experiment compares the performance of a **single-layer Perceptron** and a **Multilayer Perceptron (MLP)** on a handwritten English character dataset.  
The main goal is to evaluate how deep learning models (MLP) outperform simple linear classifiers (Perceptron) when tuned with optimal hyperparameters.

---

## 🎯 Objectives
- To implement and train a **Perceptron classifier** on the dataset.  
- To implement and train a **Multilayer Perceptron (MLP)** using `sklearn.neural_network.MLPClassifier`.  
- To perform **hyperparameter tuning** using **GridSearchCV**.  
- To compare both models using performance metrics like **accuracy**, **recall**, **F1-score**, **confusion matrix**, and **ROC-AUC**.  

---

## 🧩 Dataset
- CSV file: `english.csv` (contains image file names and labels).  
- Images are grayscale English alphabet samples located in the directory specified in the code.  
- Labels are encoded numerically (0–61) corresponding to unique characters.

---

## ⚙️ Methodology

### 1. Data Preprocessing
- Images are read using **OpenCV**, resized to **28×28**, and flattened.  
- Pixel values are normalized to the range [0, 1].  
- Labels are mapped from categorical to numeric form.  
- Dataset is split into **train** and **test** sets using `train_test_split()`.

### 2. Model Training
- **Model A:** `Perceptron()` – basic linear classifier.  
- **Model B:** `MLPClassifier()` – multi-layer neural network.  

### 3. Hyperparameter Tuning
- Parameters tuned for MLP:
  - Hidden layer sizes  
  - Learning rate  
  - Activation function (`relu`, `tanh`)  
  - Solver (`adam`, `sgd`)  
- Tuning done via **GridSearchCV** for optimal configuration.

### 4. Evaluation Metrics
- Accuracy  
- Recall  
- F1 Score  
- Confusion Matrix (visualized with **Seaborn heatmap**)  
- ROC Curve & AUC score  

---

## 📊 Results
- The **Multilayer Perceptron (MLP)** achieved higher accuracy and generalization compared to the **Perceptron** model.  
- ROC-AUC curves show improved class separation for the tuned MLP.  
- The experiment highlights the advantage of nonlinear activation and deep architecture for image-based classification tasks.

---

## 📦 Dependencies
Install all required libraries before running the notebook:

```bash
pip install numpy pandas scikit-learn matplotlib seaborn opencv-python

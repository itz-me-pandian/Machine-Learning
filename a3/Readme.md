# Assignment 3 (` Email Spam or Ham Classification using Naïve Bayes, KNN, and SVM`)

This directory contains files and scripts for Assignment 3 of the Machine Learning course. The assignment focuses on Email Spam or Ham Classification using Na¨ıve Bayes, KNN, and
 SVM.

## Contents

    1. Importing Libraries
        Essential Python libraries like pandas, numpy, matplotlib, seaborn, sklearn are imported.

    2. Reading and Exploring the Dataset
        Reads the dataset from Google Drive, explores structure, checks for missing values, and performs EDA (Exploratory Data Analysis).

    3. Data Cleaning and Preprocessing
        ◦ Missing value imputation using SimpleImputer.
        ◦ Label encoding of categorical features.
        ◦ Data normalization/standardization.
        
    4. Model Implementation
        ◦ KNN (KNN,Ball Tree,KD Tree)
        ◦ Naive Bayes Variants(Bernoulli,Gaussian,Multinomial)
        ◦ SVC
        
    6. Model Evaluation
        ◦ Accuracy
        ◦ Precision
        ◦ Recall
        ◦ Confusion Matrix
        ◦ ROC
        ◦ AUC
        
    7. Cross Fold validation
        Demonstrates how k fold validation impacts model performance.

## Dataset: 
  The Link of the dataset used in this assignment is [https://www.kaggle.com/datasets/phileinsophos/predict-loan-amount-data](https://www.kaggle.com/datasets/somesh24/spambase). The dataset used in this assignment is related to Email Spam or Ham Classification and is accessed via Google Drive. If you'd like to run the notebook locally, ensure that the dataset path is correctly specified and the required file is uploaded.

## Structure

Typical files you might find in this directory:
- `ipynb models files of 3 models`: Main code or notebook for the assignment.
- `spambase_csv.csv`: dataset (CSV).
- `output`: Output of all models(ROC,Confusion Matrix).

## How to Use

1. **Clone the Repository**
   ```bash
   git clone https://github.com/itz-me-pandian/Machine-Learning.git
   cd Machine-Learning/a3
   ```

2. **Install Requirements**
   If there is a `requirements.txt` file, install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the Assignment**
    1. Open the notebook in Google Colab or Jupyter Notebook of desired model.
    2. Mount your Google Drive if running in Colab.
    3. Ensure the dataset is available at the specified path.
    4. Run each cell in order to replicate results.

## Notes

- Make sure you have Python and the necessary libraries (e.g., numpy, pandas, scikit-learn, matplotlib, seaborn) installed.
- Refer to comments in the code for explanation of each step.
  
## Author

Developed by [itz-me-pandian](https://github.com/itz-me-pandian) as part of the Machine Learning course.

## License

This assignment code is for educational purposes.

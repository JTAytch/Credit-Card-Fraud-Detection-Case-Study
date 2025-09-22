# 💳 Credit Card Fraud Detection – End-to-End Case Study

**Author:** Joseph Tulani Aytch  
**Dataset:** [Kaggle – Credit Card Fraud Detection](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud) & [FraudTrain Dataset](https://www.kaggle.com/datasets/kartik2112/fraud-detection)  

---

## 📌 Project Overview
Credit card fraud is a major challenge for financial institutions, costing billions annually.  
This project demonstrates an **end-to-end machine learning workflow** for detecting fraudulent transactions, from **EDA and feature engineering** to **model training, hyperparameter tuning, and deployment via a Dash app prototype**.

---

## 🎯 Business Problem
- **Goal:** Accurately identify fraudulent transactions while minimizing false positives.  
- **Challenge:** Fraudulent cases are extremely rare (<1% of transactions), making recall on fraud the most critical metric.  
- **Impact:** A missed fraud = lost revenue; too many false positives = poor customer experience.

---

## 📊 Data
- **Source:** Kaggle credit card fraud datasets  
- **Size:** ~1.2M transactions (downsampled for modeling)  
- **Features:**  
  - PCA-transformed anonymized features (V1–V28)  
  - Transaction details: `amt`, `zip`, `state`, `city_pop`, `merchant`, `category`, `job`  
  - Target: `is_fraud` (0 = legitimate, 1 = fraud)  
- **Class Imbalance:** ~7,500 fraud cases vs. >1M non-fraud cases

---

## 🛠 Methods
1. **Exploratory Data Analysis (EDA)**  
   - Inspected distributions, correlations, and class imbalance  
   - Built correlation heatmaps and summary statistics  

2. **Feature Engineering**  
   - Selected key features (`merchant`, `category`, `amt`, `gender`, `zip`, `state`, `city_pop`, `job`)  
   - Applied **label encoding** and **one-hot encoding** for categorical variables  

3. **Modeling**  
   - Baseline: Random Forest Classifier on 100K sample  
   - Adjusted sampling to include **all fraud cases + 25K non-fraud** for better fraud recall  
   - Evaluated with **accuracy, precision, recall, F1-score**  

4. **Hyperparameter Tuning**  
   - Used `GridSearchCV` with parameters:  
     - `n_estimators` (100–300)  
     - `max_depth` (5–15)  
     - `min_samples_split`, `min_samples_leaf`  
   - Best model achieved **~96.5% accuracy** with improved fraud detection  

5. **Deployment Prototype**  
   - Built a **Dash app** to serve predictions  
   - Simplified input to 3 features (`amt`, `zip`, `city_pop`) for demo purposes  
   - App returns fraud prediction in real time

---

## 📈 Results
- **Accuracy:** ~96.5%  
- **Fraud Recall:** Improved significantly after resampling  
- **Key Insight:** Recall on fraud is more important than overall accuracy in this domain  
- **Best Model:** Tuned Random Forest Classifier  

---

## 📊 Visuals
- Correlation heatmap of features  
- Class distribution (fraud vs. non-fraud)  
- Confusion matrix of best model  
- ROC curve & Precision-Recall curve (recommended next step for visualization)

---

## 🚀 Next Steps
- Expand Dash app to handle more features dynamically  
- Explore alternative models (XGBoost, Neural Networks) for higher recall  
- Implement SMOTE or class weighting for imbalance handling  
- Deploy app to cloud (Heroku, Streamlit, or Azure) for live demo  

---

## 📂 Project Structure
```text
Credit-Card-Fraud-Detection-Dashboard/
├── data/                # Sample or reference datasets
├── notebooks/           # Jupyter notebooks for EDA & modeling
│   └── 01_EDA.ipynb
│   └── 02_Modeling.ipynb
├── app/                 # Dash app prototype
│   └── app.py
├── models/              # Saved models
│   └── best_RFC_model_fraud.joblib
├── images/              # Visuals (heatmaps, confusion matrix, ROC curve)
├── requirements.txt     # Dependencies
└── README.md            # Documentation
```

## 📬 Contact
For questions or collaboration:  
- **LinkedIn:** [Joseph Tulani Aytch](https://www.linkedin.com/in/tulaniaytch/)  
- **Email:** tulan94@gmail.com  

---

## 🙏 Acknowledgments
- Dataset: Kaggle Credit Card Fraud Detection (MLG-ULB) and FraudTrain variants  
- Inspiration: Dash documentation and scikit-learn examples for prototyping  

---

## 🔒 Disclaimer
This project uses anonymized and/or synthetic data. Insights and model behavior may not directly translate to production environments without domain validation and appropriate governance.

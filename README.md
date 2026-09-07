# Customer Churn Prediction App

## 📌 Project Overview

Customer churn is a critical problem for subscription-based businesses, as retaining existing customers is significantly more cost-effective than acquiring new ones.

This project builds an **end-to-end Machine Learning system** to predict customer churn probability using customer demographics, service usage, and billing data.

The solution goes beyond just modeling and focuses on the **complete ML lifecycle**, including:

- Exploratory Data Analysis (EDA)
- Feature engineering & preprocessing
- Model training and comparison
- Class imbalance handling
- Threshold optimization
- Model explainability using SHAP
- Deployment with Streamlit

Users can input customer information and receive a **real-time churn probability prediction along with model insights**.

---

## 🎥 Live Project Walkthrough

👉 https://www.youtube.com/watch?v=RKXDvzcKWL0

---

## 🚀 Live Demo

Streamlit App:  
https://customer-churn-prediction-lr-rf.streamlit.app/

---

## 📊 Dataset

This project uses the **Telco Customer Churn Dataset** available on Kaggle.

Dataset Link:  
https://www.kaggle.com/datasets/blastchar/telco-customer-churn

- **7043 customer records**
- **21 features**

### Feature Categories:

- Customer demographics (gender, partner, dependents, senior citizen)
- Account information (tenure, contract type, billing method)
- Services subscribed (internet, streaming, security, tech support)
- Billing information (monthly charges, total charges)
- Target variable: **Churn**

The goal is to build models that **predict customer churn probability** and enable data-driven retention strategies.

---

## 🛠 Tech Stack

- Python
- Pandas, NumPy
- Scikit-learn
- XGBoost
- SHAP
- Matplotlib
- Streamlit
- Joblib

---

## ⚙️ Machine Learning Pipeline

### 🔹 Numerical Features

- Tenure  
- MonthlyCharges  
- TotalCharges  

Processing:
- Missing value imputation
- Standard scaling

---

### 🔹 Categorical Features

- Gender
- Contract type
- Internet service
- Payment method
- Service-related features

Processing:
- Missing value imputation
- One-hot encoding

---

All preprocessing is handled using a **Scikit-learn ColumnTransformer**, ensuring a clean and reproducible pipeline.

---

## 🤖 Models Used

### 🔹 Logistic Regression
- Baseline interpretable model  
- High recall → good at identifying churn customers  

---

### 🔹 Random Forest
- Ensemble model  
- Captures non-linear relationships  
- Balanced performance across metrics  

---

### 🔹 XGBoost
- Gradient boosting model  
- Handles class imbalance using `scale_pos_weight`  
- Strong performance with optimized learning and regularization  

---

## 📈 Model Performance

| Model | ROC-AUC | F1 Score | Precision | Recall |
|------|--------|--------|--------|--------|
| Logistic Regression | 0.86 | 0.64 | 0.52 | 0.84 |
| Random Forest | 0.85 | 0.65 | 0.56 | 0.78 |
| XGBoost | 0.85 | 0.63 | 0.55 | 0.75 |

---

## ⚖️ Threshold Optimization

Instead of using a default threshold (0.5), different thresholds were evaluated to balance:

- Precision (avoiding false positives)
- Recall (capturing churn customers)

This allows businesses to **customize risk tolerance based on strategy**.

---

## 🔍 Model Explainability (SHAP)

To make the model interpretable, **SHAP (SHapley Additive Explanations)** was used:

- Explains **individual predictions**
- Identifies **global feature importance**
- Helps understand **why a customer is likely to churn**

### Key Insights from SHAP:

- 📉 Low tenure → higher churn risk  
- 📉 Month-to-month contracts → strong churn driver  
- 📈 Higher monthly charges → increased churn probability  
- ❌ Lack of services (security, tech support) → higher churn  

---

## 📊 Key Insights

### 📌 Contract Type
Customers on **month-to-month contracts** show the highest churn probability.

### 📌 Customer Tenure
Customers with shorter tenure are significantly more likely to churn.

### 📌 Monthly Charges
Higher monthly charges correlate with increased churn.

### 📌 Internet Service Type
Customers with **fiber optic service** have higher churn rates.

### 📌 Value-added Services
Customers without:
- Online Security  
- Tech Support  
- Device Protection  

are more likely to churn.

---

## 💡 Business Recommendations

Based on the model insights:

- Encourage **long-term contracts** via incentives  
- Offer **bundled services** to improve retention  
- Provide **targeted offers to high-paying customers**  
- Focus retention strategies on **new customers with low tenure**  

---

## 🌐 Deployment

The model is deployed using **Streamlit**, allowing users to:

- Input customer data  
- Get churn probability instantly  
- View model explanations using SHAP  

---

## 📌 Conclusion

This project demonstrates how to build a **production-ready ML solution** that combines:

- Predictive modeling  
- Business understanding  
- Explainability  
- Deployment  

It highlights the importance of going beyond modeling to deliver **actionable business insights**.

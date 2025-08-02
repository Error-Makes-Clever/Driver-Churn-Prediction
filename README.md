# 🚗 Driver Churn Prediction – ML Project

Predicting whether a driver will **churn (leave the platform)** using advanced machine learning techniques, based on **driver demographics**, **performance**, **income**, and more.

![Driver Churn Banner](https://img.shields.io/badge/ML-Driver%20Churn%20Prediction-blue?style=for-the-badge)  
![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)  
![ML Models](https://img.shields.io/badge/Models-XGBoost%2C%20LightGBM%2C%20RF%2C%20GB-orange.svg)

---

## 📊 Dataset Overview

| Feature               | Description                                                                          |
|-----------------------|--------------------------------------------------------------------------------------|
| MMMM-YY               | Reporting month-year                                                                |
| Driver_ID             | Unique identifier for each driver                                                   |
| Age, Gender           | Demographic details (Gender: 0=Male, 1=Female)                                      |
| City, Education_Level | Operational details (Edu: 0=10+, 1=12+, 2=Graduate)                                 |
| Income                | Average monthly income of driver                                                    |
| Date Of Joining       | When the driver joined                                                              |
| LastWorkingDate       | When the driver left                                                                |
| Grade, Designation    | Rank and level at joining/reporting time                                            |
| Total Business Value  | Revenue contribution (negative implies cancellations/adjustments)                   |
| Quarterly Rating      | Driver rating (1–5)                                                                 |

---

## 📈 Exploratory Data Insights

### 👤 Demographics
- **Majority drivers** aged 28–38 (right-skewed).
- Gender & education level → **minimal impact on churn**.
- **Most churners** joined with **Designation 1**.

### 💰 Income & Business Value
- Avg income ₹40k–₹70k, skewed distribution.
- **Income growth = retention** (Only 43 got raises!).
- High total business value → **less likely to churn**.

### ⏳ Tenure & Rating
- Short-tenure drivers churn more.
- Ratings of **1 or 2 → high churn**; **no drivers rated 5**.
- High **grade (4,5)** → better performance & retention.

### 🏙️ City Insights
- **C13** has highest churn rate (>80%); **C29** has lowest.
- **C17** shows performance drop, **C29** improves steadily.
- City-wise churn & performance help **target retention** strategies.

---

## **🧠 Modeling Observations**

### 🔍 Model Comparison:

To address class imbalance in the churn variable, **SMOTE (Synthetic Minority Over-sampling Technique)** was applied before training the models.

| Model             | F1 Score   | Accuracy   | Precision  | Recall     | **AUC**    |
| ----------------- | ---------- | ---------- | ---------- | ---------- | ---------- |
| **LightGBM ⭐**    | **0.9612** | **0.9476** | **0.9657** | **0.9568** | **0.9764** |
| Gradient Boosting | 0.9553     | 0.9392     | 0.9538     | 0.9568     | 0.9764     |
| XGBoost           | 0.9502     | 0.9329     | 0.9591     | 0.9414     | 0.9749     |
| Random Forest     | 0.9354     | 0.9120     | 0.9325     | 0.9383     | 0.9642     |

---

### ✅ Final Model: **LightGBM**

> LightGBM demonstrated the most balanced and high-performing metrics across **F1 Score**, **Precision**, **Recall**, and **AUC** on the test set.

| Metric             | Value  |
| ------------------ | ------ |
| **Accuracy**       | 94.76% |
| **F1 Score**       | 0.961  |
| **Precision**      | 96.6%  |
| **Recall**         | 95.7%  |
| **AUC**            | 0.9764 |
| **AUC-PR**         | 0.9895 |
| **Best Threshold** | 0.12   |

---

## 🔍 Key Business Insights

- **Top churn factors**: Low performance rating, no income/rating growth, short tenure.
- **Tenure**, **total business value**, and **Quarterly Rating** are **strong negative churn indicators**.
- **Cities C13, C17, and C2** need urgent churn-reduction strategies.
- **High-grade, high-income drivers** must be prioritized for **retention efforts**.
- **Income and rating improvements** → highly associated with lower churn.

---

## 🔧 Feature Importance (Top Drivers of Prediction)

- 🏆 **Quarterly Rating**
- 📅 **Joining Year**
- 💸 **Total Income & Business Value**
- 🎖️ **Grade**
- ⏳ **Tenure**

---

## 📂 Project Structure
```
Driver-Churn-Prediction/
├── Driver_Info.csv # Raw dataset
├── Driver_Churn_Prediction.ipynb # Full analysis notebook
├── README.md # Project overview
```

## 📦 Tools & Technologies

- **Python 3.12**
- **Pandas, NumPy, Matplotlib, Seaborn**
- **Scikit-learn, XGBoost, LightGBM, imbalanced-learn (SMOTE)**
- **EDA, Feature Engineering, Model Tuning**

---

## 📚 Future Enhancements

- Integrate **SHAP values** for explainable AI insights.
- Deploy via **Streamlit** or **Flask** for real-time churn prediction.
- Retrain periodically using new data and **drift detection**.


## ⭐ Support
If you found this project helpful, consider giving it a ⭐ star on GitHub!

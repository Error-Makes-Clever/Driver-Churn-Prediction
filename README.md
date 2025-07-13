# 🚕 Driver Churn Prediction

Predicting whether a driver is likely to leave (churn) based on historical performance, demographics, and behavioral patterns.

![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Wrangling-green?logo=pandas)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualizations-orange?logo=seaborn)

---

## 📌 Project Overview

This project analyzes a dataset of over 19,000 records containing detailed information on drivers, including:
- Demographics (Age, Gender, City)
- Employment history (Joining date, Last working date, Designation)
- Monthly performance (Income, Business value, Ratings)

The objective is to:
- Identify key factors that contribute to driver churn
- Create meaningful features through feature engineering
- Visualize trends and insights across various attributes

---

## 📊 Dataset Description

| Feature              | Description |
|----------------------|-------------|
| `Driver_ID`          | Unique driver identifier |
| `Age`, `Gender`      | Demographic features |
| `City`               | Location code |
| `Education_Level`    | 10+ / 12+ / Graduate |
| `Income`             | Monthly average income |
| `Joining Designation`, `Grade` | Role info |
| `Total Business Value` | Monthly performance value |
| `Quarterly Rating`   | Driver rating from 1 to 5 |
| `LastWorkingDate`    | Indicates if the driver churned |

---

## 🔧 Data Cleaning & Feature Engineering

- ✅ Handled missing values using **KNN Imputation**
- 📆 Converted date columns to datetime objects
- 🧠 Engineered new features:
  - `Churned` (1 if LastWorkingDate exists)
  - `Has_Income_Increased`, `Has_Rating_Increased`
  - `Tenure` (days between joining and last working)
  - `Is_Valuable_Driver` based on Business vs Income
- 🧹 Removed duplicates & inconsistencies

---

## 📈 Exploratory Data Analysis (EDA)

Visual insights using **Seaborn** and **Matplotlib**:

- **Churn Distribution**: ~68% of drivers churned.
- **Business Value vs Churn**: Retained drivers generated significantly more value.
- **Gender Churn Split**: Both genders affected, slightly higher in males.
- **City-wise Distribution**: City `C20` had the highest number of drivers.
- **Joining Trends**: Most joined in 2018; churn peaked in 2019.
- **Tenure**: Churned drivers had shorter tenures on average.

<div align="center">
  <img src="https://github.com/manoj-sys-core/your-repo/assets/driver_churn_eda.png" alt="EDA Summary" width="700"/>
</div>

---

## 🔍 Key Findings

- 🔻 **Low tenure & low business value** strongly correlate with churn.
- 📈 Drivers who **improved rating or income** were less likely to churn.
- 📍 Driver retention strategies should focus on **new joiners and underperformers**.
- ⭐ Valuable drivers (high business vs income) should be **monitored closely** for early churn signs.

---

## 📁 Project Structure

```
├── Driver_Info.csv
├── driver_churn_analysis.ipynb
├── README.md
```

---

## 🧠 Future Scope

- Train ML models (Random Forest, XGBoost) for churn prediction
- Use SHAP for explainable AI on churn drivers
- Integrate with dashboarding tools (e.g., Streamlit)

---

## 🛠️ Tech Stack

- **Python** (Pandas, NumPy)
- **Matplotlib / Seaborn** (EDA & Viz)
- **Scikit-learn** (KNN Imputer, Pipeline)
- **Jupyter Notebook**

---

## 👨‍💻 Author

**Manoj S**  
📧 manojcs6317@gmail.com  
🌐 [GitHub](https://github.com/manoj-sys-core)

---

> ⭐ *If you liked this project, consider giving it a star on GitHub!*

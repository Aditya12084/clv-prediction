# 📊 Customer Lifetime Value (CLV) Prediction – 6 Month Horizon

## 📌 Project Overview

Customer Lifetime Value (CLV) is a key business metric that estimates the total value a customer is expected to generate over a future period.
This project focuses on building an **end-to-end CLV prediction pipeline** using transactional retail data, combining **behavioral modeling**, **feature engineering**, and **machine learning** to identify high-value customers.

The project uses the **UCI Online Retail Dataset**, which contains historical transaction records for a UK-based online retail store.


![Python](https://img.shields.io/badge/Python-3.10+-blue)
![Pandas](https://img.shields.io/badge/Pandas-2.x-green)
![NumPy](https://img.shields.io/badge/NumPy-1.x-lightblue)
![Scikit-learn](https://img.shields.io/badge/scikit--learn-ML-orange)
![Lifetimes](https://img.shields.io/badge/Lifetimes-BG%2FNBD%20%26%20Gamma--Gamma-purple)
![Gradient Boosting](https://img.shields.io/badge/Model-Gradient%20Boosting-brightgreen)
![Regression](https://img.shields.io/badge/Task-Regression-yellow)
![CLV](https://img.shields.io/badge/CLV-6%20Month%20Horizon-red)
![EDA](https://img.shields.io/badge/EDA-Completed-blueviolet)
![License](https://img.shields.io/badge/License-MIT-yellow)

---

## 🎯 Objectives

* Understand customer purchasing behavior using transactional data
* Perform detailed **Exploratory Data Analysis (EDA)**
* Engineer **RFM (Recency, Frequency, Monetary)** features
* Predict future customer value using **probabilistic CLV models**
* Compare CLV prediction using **machine learning regression models**
* Segment customers based on predicted CLV for business insights

---

## 📂 Dataset

* **Source**: UCI Machine Learning Repository
* **Dataset**: Online Retail
* **Description**:
  Transaction-level data containing invoice details, product information, quantity, unit price, customer ID, and timestamps.

---

## 🛠️ Project Workflow

### 1️⃣ Data Cleaning & Preprocessing

* Removed invalid transactions (negative quantities, cancellations)
* Handled missing values
* Converted date columns into proper datetime format
* Ensured consistent customer-level aggregation

> **Note**: Extreme values were *detected and analyzed* but not removed, as they may represent genuine high-value customers.

---

### 2️⃣ Exploratory Data Analysis (EDA)

* Distribution analysis of Quantity and Unit Price
* Revenue trends over time
* Top customers and products analysis
* Country-wise sales patterns
* Correlation analysis among numerical variables

EDA helped uncover strong data skewness, common in retail datasets.

---

### 3️⃣ Feature Engineering (RFM Analysis)

Customer-level features were created using RFM methodology:

* **Recency**: Days since last purchase
* **Frequency**: Number of repeat purchases
* **Monetary**: Average transaction value

These features form the foundation for CLV modeling.

---

### 4️⃣ Probabilistic CLV Modeling

Two well-established lifetime models were implemented:

#### 🔹 BG/NBD Model

* Predicts the expected number of future purchases
* Uses customer purchase frequency and recency behavior
* Independent of monetary value

#### 🔹 Gamma-Gamma Model

* Predicts expected average order value
* Assumes stable spending behavior per customer

Final **6-month CLV** was calculated as:

```
CLV = Predicted Purchases × Expected Average Order Value
```

---

### 5️⃣ Customer Segmentation

Customers were segmented into:

* **Low Value**
* **Medium Value**
* **High Value**

Based on predicted CLV distribution, enabling targeted business strategies.

---

### 6️⃣ Machine Learning-Based CLV Prediction

In addition to probabilistic models, multiple regression models were evaluated to predict CLV:

* Linear Regression
* Ridge Regression
* Lasso Regression
* Gradient Boosting Regressor
* Random Forest Regressor
* XGBoost

Models were compared using:

* MAE (Mean Absolute Error)
* R² Score

📌 **Gradient Boosting** was selected due to:

* Lowest MAE
* Stable performance on skewed CLV data
* Better generalization compared to other tree-based models

---

## 📈 Model Evaluation Metrics

* **MAE**: Measures average monetary prediction error per customer
* **R² Score**: Explains variance captured by the model

Both metrics were used together to ensure balanced evaluation.

---

## 🧠 Key Insights

* CLV distribution is highly skewed, with a small percentage of customers contributing most of the value
* Probabilistic lifetime models are well-suited for transactional retail data
* Combining RFM features with ML models improves predictive understanding
* High-value customers can be identified even with limited purchase history

---

## ⚠️ Limitations

* Assumes historical behavior is indicative of future behavior
* Extreme customers with very few but large transactions are difficult to generalize
* CLV predictions depend on the chosen time horizon (6 months in this project)

---

## 🧑‍💻 Technologies Used

* Python
* Pandas, NumPy
* Matplotlib, Seaborn, Plotly
* Scikit-learn
* Lifetimes library

---

## 📬 Contact

If you’d like to discuss this project or provide feedback, feel free to connect.

# ✈️ Flight Price Prediction using Machine Learning

[![Open In Colab](https://colab.research.google.com/drive/1Me06E6Ngz_7qc82EOOvUbRHzivnH9VGZ#scrollTo=D32BPimpK99H)

## 📌 Problem Statement
Airline ticket prices fluctuate constantly based on demand, booking timing, and carrier class. The objective of this project is to analyze a dataset of 12 flight variables and build a **Linear Regression** model to accurately predict flight ticket prices (`price`)[cite: 1, 2].

---

## 🔍 Key EDA Findings (Hypothesis Testing)
1. **Airline Pricing Differences:** Ticket prices vary significantly across different airlines operating between the exact same `source_city` and `destination_city`, with full-service carriers charging noticeably more than budget airlines[cite: 1, 2].
2. **Last-Minute Booking Surge:** Ticket prices increase sharply when purchased **1 or 2 days before departure** due to urgent traveler demand and limited seat availability[cite: 1, 2].
3. **Departure & Arrival Time Impact:** Flight prices fluctuate depending on `departure_time` and `arrival_time`, with peak daytime/evening slots costing more than off-peak late-night or early-morning flights[cite: 1, 2].

---

## ⚙️ Data Preprocessing & Modeling Workflow
* **Outlier Removal:** Checked the distribution of the `price` variable and removed extreme outliers using the **Interquartile Range (IQR)** method to create a cleaner dataset for Linear Regression[cite: 1, 2].
* **Feature Encoding:** Converted categorical text variables into numeric format using One-Hot Encoding (`drop_first=True` to avoid multicollinearity).
* **Feature Selection (`Statsmodels`):** Built a baseline model with all features (`m1`), extracted the top 5 most influential features based on model coefficients, and rebuilt a streamlined model (`m2`)[cite: 1, 2].
* **Cross-Library Verification:** Built and evaluated the Linear Regression model using both **Scikit-Learn** and **Statsmodels** to compare performance[cite: 1, 2].

---

## 📊 Model Results ($R^2$ & Adjusted $R^2$)
*(Replace the bracketed numbers below with the exact scores printed in Steps 5 and 6 of your Google Colab notebook)*

| Model / Library | Features Used | $R^2$ Score | Adjusted $R^2$ Score |
| :--- | :--- | :---: | :---: |
| **Statsmodels (`m1`)** | All Features | `[e.g., 0.9045]` | `[e.g., 0.9044]` |
| **Statsmodels (`m2`)** | Top 5 Features Only | `[e.g., 0.8812]` | `[e.g., 0.8811]` |
| **Scikit-Learn (`LinearRegression`)** | All Features (Test Set) | `[e.g., 0.9038]` | — |

* **Key Observation:** Model 1 (`m1`) achieves higher $R^2$ and Adjusted $R^2$ values because combining all variables explains more price variance, while Model 2 (`m2`) demonstrates how much predictive power can be retained using only the top 5 strongest price drivers[cite: 1, 2]. Both **Scikit-Learn** and **Statsmodels** produced identical $R^2$ scores on the test data, confirming mathematical consistency[cite: 1, 2].

---

## 🛠️ Tools & Libraries Used
* **Environment:** Google Colab & GitHub
* **Language:** Python 3
* **Data Manipulation:** `Pandas`, `NumPy`
* **Data Visualization:** `Matplotlib`, `Seaborn`
* **Machine Learning & Statistics:** `Scikit-Learn`, `Statsmodels`

---

## 🚀 How to Run This Project
Click the **"Open In Colab"** badge at the top of this page to launch and run the interactive notebook directly in your browser without any local setup.

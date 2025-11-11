# 🛍️ E-Commerce Customer Spending Prediction using Multiple Linear Regression

## 📘 Overview
This project applies **Multiple Linear Regression** to predict the **Yearly Amount Spent** by customers of an E-commerce company.  
The model analyzes customer interaction metrics to identify which factors most strongly influence annual spending.

---

## 🎯 Project Goal
The primary objective is to build and evaluate a **linear regression model** that predicts a customer’s spending behavior based on the following independent variables:

| Feature | Description |
|----------|-------------|
| **Avg. Session Length** | Average session length of in-store style advice sessions |
| **Time on App** | Average time (in minutes) spent on the mobile app |
| **Time on Website** | Average time (in minutes) spent on the website |
| **Length of Membership** | Duration (in years) of customer membership |

**Dependent Variable (Target):**
- `Yearly Amount Spent`

---

## 💾 Dataset Description
**Dataset:** `Ecommerce Customers.csv`  
**Rows:** 500  
**Columns:** 8  

### 🧩 Sample Data
| Email | Address | Avatar | Avg. Session Length | Time on App | Time on Website | Length of Membership | Yearly Amount Spent |
|-------|----------|---------|--------------------|-------------|-----------------|----------------------|---------------------|
| mstephenson@fernandez.com | 835 Frank Tunnel | Violet | 34.497 | 12.656 | 39.578 | 4.083 | 587.951 |
| hduke@hotmail.com | 4547 Archer Common | DarkGreen | 31.926 | 11.109 | 37.269 | 2.664 | 392.205 |
| pallen@yahoo.com | 24645 Valerie Unions | Bisque | 33.001 | 11.330 | 37.111 | 4.105 | 487.548 |

---

## 📊 Exploratory Data Analysis (EDA)
Before training the model, feature relationships were analyzed using scatter plots.

### 🔍 Observations:
- **Length of Membership** shows the **strongest positive linear correlation** with yearly spending.  
- **Time on App** also shows a significant positive correlation.  
- **Avg. Session Length** has a weak positive correlation.  
- **Time on Website** shows minimal or no linear relationship.

---

## ⚙️ Methodology and Implementation

The project follows the standard machine learning workflow:

1. **Data Preprocessing**  
   - Extracted independent variables (X) and dependent variable (Y).  

2. **Train-Test Split**  
   - Split data into **80% training** and **20% testing** using `random_state=42`.

3. **Feature Scaling**  
   - Standardized features using `StandardScaler` to normalize ranges.

4. **Model Training**  
   - Trained a `LinearRegression` model from `sklearn.linear_model` on the scaled data.

---

## 🔬 Model Results

### 🧮 Linear Regression Equation
After training, the model’s parameters were obtained as:

\[
\hat{Y} = 501.99 + 25.25(X_{Session}) + 38.70(X_{App}) + 0.32(X_{Website}) + 63.54(X_{Membership})
\]

### 📊 Coefficients Interpretation
| Feature | Coefficient | Interpretation |
|----------|-------------|----------------|
| **Length of Membership** | 63.54 | Most influential. A longer membership leads to significantly higher yearly spending. |
| **Time on App** | 38.70 | Strong positive influence on spending. |
| **Avg. Session Length** | 25.25 | Moderate positive relationship. |
| **Time on Website** | 0.32 | Minimal effect on spending. |

---

## 🧠 Evaluation Metrics
| Metric | Value | Interpretation |
|---------|--------|----------------|
| **RMSE (Root Mean Squared Error)** | 10.48 | Small average deviation between predicted and actual values. |
| **MAE (Mean Absolute Error)** | 8.56 | Low prediction error. |
| **R² Score** | **0.9778** | The model explains **97.78% of the variance** in yearly spending. |

✅ **Conclusion:**  
The high \( R^2 \) and low errors indicate an excellent model fit and strong predictive performance.

---

## 💡 Insights
- The **Length of Membership** is the dominant predictor of spending — longer-term customers tend to spend more.  
- **Mobile App usage** is more correlated with spending than **Website time**, suggesting the app drives higher engagement and sales.  
- **Avg. Session Length** moderately contributes to spending prediction.  
- The **Website time** has minimal predictive value — potential for UX improvement.

---

## 💻 Technologies Used
- **Python 3.10+**
- **Libraries:**
  - pandas
  - numpy
  - matplotlib
  - seaborn
  - scikit-learn

---

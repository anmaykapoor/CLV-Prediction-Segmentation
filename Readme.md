#  Customer Lifetime Value Prediction & Segmentation

## 📌 Project Overview
This project focuses on predicting the **Customer Lifetime Value (CLV)** and segmenting customers for a UK-based online retail company using real-world e-commerce data.

The goal is to:
- Predict how much a customer might spend in the future using historical behavioral data.
- Segment customers into groups based on purchasing behavior for better targeting.

> 📂 **Dataset Used**: [Online Retail II Dataset (Kaggle)](https://www.kaggle.com/datasets/lakshmi25npathi/online-retail-dataset)  
> 🗓️ Contains transactions between **2009-2011** from a UK-based giftware retailer.

---

## 🧹 Step 1: Data Cleaning
- Removed missing Customer IDs
- Filtered out records with negative Quantity or UnitPrice
- Handled outliers using upper quantile caps
- Created `TotalPrice = Quantity × Price`

📊 Final Shape: `(805549, 9)` after cleaning

---

## 🔍 Step 2: Exploratory Data Analysis (EDA)
- Visualized distributions of Quantity, Price, and Total Price
- Boxplots and heatmaps helped identify correlations and outliers
- Key Insight: High variance in customer spending behavior

---

## 🧠 Step 3: Feature Engineering (RFM + Extras)
Created a robust **RFM table** using:
- **Recency** (days since last purchase)
- **Frequency** (no. of invoices)
- **Monetary** (total spend)

➕ Additional engineered features:
- Product Diversity
- Discount Sensitivity
- Average Order Value
- Weekend Shopper Flag

📊 Final RFM Table Shape: `(5878, 6)`

---

## ⚙️ Step 4: Model Development - Predicting CLV
Built and compared multiple models including:
- **Random Forest Regressor**
- **Gradient Boosting Regressor**
- **Decision Tree Regressor**
- **K-Nearest Neighbors (KNN)**  
> _(Note: Linear and Ridge Regression were removed due to negative R² scores. KNN also performed poorly due to high RMSE and low R².)_


### 🔧 Hyperparameter Tuning (Random Forest)
Used `GridSearchCV` to improve Random Forest performance.

---

## 📈 Final Model Performance

| Model                  | R² Score | RMSE (₹)       |
|------------------------|----------|----------------|
| Random Forest          | 0.8888   | ₹6,390.55      |
| Tuned Random Forest    | 0.8922   | ₹6,293.35      |
| Decision Tree          | 0.9410   | ₹4,656.12      |
| Gradient Boosting      | **0.9703** | **₹3,300.89** |
| K-Nearest Neighbors    | 0.2109   | ₹17,025.66     |


✅ **Gradient Boosting Regressor** was selected as the final CLV prediction model.

---

## 🧩 Step 5: Customer Segmentation
- Used **KMeans Clustering** on scaled RFM data
- Determined optimal clusters using **Elbow Method**
- Segmented customers into **4 clusters**
- Visualized segments based on Recency and Monetary

---

## ✅ Final Takeaways
- Gradient Boosting emerged as the most accurate model for predicting Customer Lifetime Value (CLV), with an R² of 0.97 and lowest RMSE.
- Decision Tree also performed strongly, indicating its potential in similar retail prediction tasks.
- KMeans clustering revealed 4 distinct customer groups, helping differentiate between high and low-value segments.
- Engineered features like Product Diversity and Weekend Shopper added valuable behavioral insights.
- This solution can directly support **targeted marketing**, **loyalty initiatives**, and **resource optimization** based on predicted CLV and customer segments.




---

## 👤 Author
**Anmay Kapoor**  
Data Science Intern  
Email: [anmaykapoor15@gmail.com] | LinkedIn: [https://www.linkedin.com/in/anmay-kapoor-b87702154/]


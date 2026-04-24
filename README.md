# 🚲 Bike Sharing Demand Prediction

An end-to-end Data Science project aimed at analyzing and predicting daily bike rental demand. This project uses the **Bike Sharing Dataset** to understand how environmental factors (weather, temperature, humidity) and seasonal settings influence rental patterns.

---

## 📊 Project Overview
Bike-sharing systems are a modern version of traditional bike rentals where the entire process is automated. This project focuses on the **Daily Dataset**, treating the system as a virtual sensor network to detect city mobility patterns and predict future demand.

## 🛠️ Tech Stack
- **Language:** Python (Google Colab)
- **Libraries:** Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn.
- **Models Used:** Random Forest Regressor.

## 🧹 Workflow
1. **Data Cleaning:** Handled missing values and verified data types.
2. **Exploratory Data Analysis (EDA):** Visualized seasonal trends, holiday impacts, and correlation between weather features (temp, hum, windspeed) and bike counts.
3. **Preprocessing:** Feature engineering and scaling for better model performance.
4. **Hyperparameter Tuning:** Used `GridSearchCV` to optimize the Random Forest model.

## 📈 Key Results
The model demonstrates high predictive power, especially after tuning the Random Forest regressor.

| Metric | Training Set | Test Set |
| :--- | :---: | :---: |
| **R² Score** | **0.999** | **0.997** |
| **MAE** | 36.082 | 66.209 |
| **RMSE** | 57.459 | 100.764 |

> **Conclusion:** The Random Forest model effectively captures the variance in bike rentals, making it a reliable tool for forecasting.

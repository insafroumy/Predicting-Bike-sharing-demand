# 🚲 Bike Sharing Demand Prediction
 
An end-to-end Data Science project aimed at analyzing and predicting daily bike rental demand. This project uses the **Bike Sharing Dataset** to understand how environmental factors (weather, temperature, humidity) and seasonal settings influence rental patterns.
 
---
 
## 📊 Project Overview
 
Bike-sharing systems are a modern version of traditional bike rentals where the entire process is automated. This project focuses on the **Daily Dataset**, treating the system as a virtual sensor network to detect city mobility patterns and predict future demand.
 
---
 
## 🛠️ Tech Stack
 
- **Language:** Python (Google Colab)
- **Libraries:** Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn
- **Models Used:** Random Forest Regressor
- **Techniques:** ColumnTransformer Pipeline, StandardScaler, SimpleImputer, GridSearchCV
---
 
## 🧹 Workflow
 
1. **Data Loading & Cleaning:** Renamed columns for clarity, checked for duplicates and null values (dataset was clean), and dropped irrelevant columns (`date`, `instant`, `casual_users`, `registered_users`).
2. **Exploratory Data Analysis (EDA):** Visualized feature correlations using a heatmap to understand relationships between weather features (temp, humidity, windspeed) and total rentals.
3. **Train/Test Split:** Split data into training and test sets using `train_test_split` with `random_state=42`.
4. **Preprocessing Pipeline:** Built a `ColumnTransformer` pipeline using `SimpleImputer` (median strategy) and `StandardScaler` for all numeric features.
5. **Model Training:** Integrated the preprocessor with a `RandomForestRegressor` inside a `make_pipeline` for a clean, leak-free workflow.
6. **Baseline Evaluation:** Evaluated the default Random Forest model before tuning.
7. **Hyperparameter Tuning:** Used `GridSearchCV` (cv=3) to optimize `max_depth`, `n_estimators`, `min_samples_leaf`, `max_features`, and `oob_score`.
8. **Final Evaluation:** Evaluated the best model from GridSearch on both training and test sets.
---
 
## 📈 Key Results
 
### Default Model (Before Tuning)
 
| Metric | Training Set | Test Set |
| :--- | :---: | :---: |
| **R² Score** | **0.981** | **0.892** |
| **MAE** | 182.338 | 419.125 |
| **RMSE** | 264.256 | 644.579 |
 
### Best Model (After GridSearchCV Tuning)
 
**Best Parameters:** `max_depth=15`, `max_features='sqrt'`, `min_samples_leaf=2`, `n_estimators=100`, `oob_score=True`
 
| Metric | Training Set | Test Set |
| :--- | :---: | :---: |
| **R² Score** | **0.958** | **0.880** |
| **MAE** | 275.042 | 464.581 |
| **RMSE** | 394.944 | 680.557 |
 
> **Conclusion:** The Random Forest model captures a strong portion of variance in bike rentals (R²=0.880 on test set), making it a reliable baseline for demand forecasting. Further improvements could be explored through additional feature engineering or trying other ensemble methods.

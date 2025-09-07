# Chili Pepper Scoville Prediction 🌶️  

## 📌 Overview  
This project predicts the **Scoville Heat Units (SHU)** of chili peppers based on physical, chemical, and environmental attributes.  
The dataset comes from a Kaggle competition and includes features such as size, weight, pericarp thickness, seed count, capsaicin content, vitamin C, sugar, moisture, firmness, color, and harvest conditions.  

The workflow covers:  
- Exploratory Data Analysis (EDA)  
- Data cleaning, handling of missing values, and feature engineering  
- Preprocessing with pipelines (scaling, encoding, imputation)  
- Regression modeling (linear and tree-based models)  
- Model evaluation using cross-validation and Mean Absolute Error (MAE)  

---

## 📂 Dataset  
- **Training set**: 1000 samples, 15 columns  
- **Test set**: 800 samples, 14 columns (no SHU target)  
- **Target variable**: `Scoville Heat Units (SHU)`  

### Features  
- **Physical**: Length, Width, Weight, Pericarp Thickness, Seed Count, Firmness  
- **Chemical**: Capsaicin Content, Vitamin C Content, Sugar Content, Moisture Content  
- **Categorical**: Color, Harvest Time  
- **Environmental**: Avg. Daily Temperature During Growth, Avg. Temperature During Storage  

---

## 🛠️ Skills & Tools Demonstrated  
- **Python**: pandas, NumPy, matplotlib, seaborn  
- **Machine Learning**: scikit-learn (Pipelines, ColumnTransformer, Random Forest, Ridge, Gradient Boosting), XGBoost  
- **EDA & Feature Engineering**: handling missing data, outlier detection, categorical encoding, scaling  
- **Model Evaluation**: cross-validation, MAE scoring  
- **Pipeline Design**: integrating preprocessing and modeling for reproducibility  
---

## 🔎 Analysis Workflow  

### 1. Data Exploration  
- Identified missing values: most features missing 1–2 values, while **Average Temperature During Storage** had ~65% missing  
- Found unrealistic values (e.g., Pericarp Thickness = 0)  
- Visualized distributions, correlations, and outliers  
<img width="684" height="484" alt="image" src="https://github.com/user-attachments/assets/271c93e2-0105-40be-8010-7f8464e70e46" />
<img width="684" height="484" alt="image" src="https://github.com/user-attachments/assets/eabf1541-e7b3-440e-83ec-cc4e38a527af" />
<img width="1103" height="1010" alt="image" src="https://github.com/user-attachments/assets/b1fdf9d6-2798-4446-aa0c-65cf6f3fbf22" />
<img width="1784" height="1484" alt="image" src="https://github.com/user-attachments/assets/360d1e72-6de4-430d-8b43-d28e64f8b822" />
<img width="1184" height="584" alt="image" src="https://github.com/user-attachments/assets/f9699dfd-0e4b-464d-9f37-a27241e0e2da" />
<img width="1583" height="1584" alt="image" src="https://github.com/user-attachments/assets/0615cde6-1f9e-4dff-b86c-7ef063f49feb" />

### 2. Data Cleaning & Feature Engineering  
- Imputed or dropped missing values depending on importance  
- Encoded categorical variables (`color`, `Harvest Time`) using OneHotEncoding  
- Standardized numerical features via `StandardScaler`  
- Built preprocessing pipelines with `ColumnTransformer`  

### 3. Modeling  
Implemented and compared multiple regression models:  
- Linear Regression  
- Ridge Regression  
- Random Forest Regressor  
- Gradient Boosting Regressor  
- XGBoost Regressor  

### 4. Evaluation  
- Metric: **Mean Absolute Error (MAE)**  
- Used **cross-validation** for model robustness  
- Observations:  
  - **Tree-based models** (Random Forest, Gradient Boosting, XGBoost) outperformed linear models  
  - Linear models struggled with feature nonlinearity and outliers  
  - Feature importance plots highlighted Capsaicin Content, Weight, and Pericarp Thickness as strong predictors  

---

## 📊 Key Results & Insights  
- **Random Forest and Gradient Boosting** delivered the best predictions with the lowest MAE  
- Capsaicin Content was the strongest feature for predicting SHU, as expected  
- Some features (e.g., Avg. Storage Temperature) contained too many missing values to be useful  
- Pipelines streamlined preprocessing and made it easy to test multiple models  







# Banana Quality Classification 🍌  

## 📌 Overview  
This project applies supervised machine learning to predict **banana quality** (good vs. bad) based on physical and chemical attributes. The dataset comes from a Kaggle competition made by the lecturer, and includes features such as size, weight, sweetness, softness, ripeness, and acidity.  

The analysis covers:  
- Data exploration and visualization  
- Feature selection and cleaning  
- Train/validation split with scaling  
- Model training and hyperparameter tuning  
- Performance evaluation across multiple classifiers  

The best model (SVC with RBF kernel, C=10) achieved an accuracy of ~97.9%.  

---

## 📂 Dataset  
- **Source**: Kaggle competition dataset (`train.csv`, `test.csv`)  
- **Training set**: 2800 samples, 9 features + target (`Quality`)  
- **Test set**: 1200 samples, 9 features  
- **Target variable**: `Quality` (0 = bad, 1 = good)  

Key features:  
- Size  
- Weight  
- Sweetness  
- Softness  
- HarvestTime  
- Ripeness  
- Acidity  
- Peel Thickness  
- Banana Density  

---

## 🛠️ Skills & Tools Demonstrated  
- **Python**: pandas, NumPy, matplotlib, seaborn  
- **Machine Learning**: scikit-learn (SVC, Logistic Regression, KNN, Random Forest)  
- **EDA & Feature Selection**: histograms, boxplots, violinplots, pairplots, correlation analysis  
- **Model Evaluation**: cross-validation, accuracy scoring, hyperparameter tuning
  
---

## 🔎 Analysis Workflow  

### 1. Data Exploration  
- Verified **no missing values**  
- Histograms, boxplots, violinplots and pairplots showed distribution differences between good and bad bananas  
- Correlation heatmap indicated **Peel Thickness** and **Banana Density** had near-zero correlation → removed from feature set  
- Features like **Sweetness, Weight, HarvestTime, and Ripeness** showed strong predictive potential  
<img width="1478" height="982" alt="image" src="https://github.com/user-attachments/assets/70b3340c-e12e-49c4-a7e0-6dc94e582d40" />
<img width="1779" height="1074" alt="image" src="https://github.com/user-attachments/assets/d6e75b15-102d-451c-ba6d-9fd8b0510b3b" />
<img width="873" height="777" alt="image" src="https://github.com/user-attachments/assets/3138f5f8-7d7b-47ff-850e-0a485b6aa0d3" />
<img width="1984" height="1766" alt="image" src="https://github.com/user-attachments/assets/fc9d5bd0-5d47-47f1-9639-e89e2cd4d969" />
<img width="1184" height="584" alt="image" src="https://github.com/user-attachments/assets/9bd10753-9025-4c08-95c2-ca2ac704137c" />

### 2. Data Cleaning & Preprocessing  
- Removed non-informative features  
- Standardized features using `StandardScaler`  
- Split into training and validation sets for model evaluation  

### 3. Modeling  
Tested multiple classifiers with hyperparameter tuning:  
- **Support Vector Classifier (SVC, RBF kernel)** → best accuracy (~97.9% with C=10)  
- **Logistic Regression** → ~87.6% accuracy  
- **K-Nearest Neighbors (KNN)** → ~94.6% accuracy (optimal k=5)  
- **Random Forest** → ~95.5% accuracy (n_estimators=100)
<img width="784" height="383" alt="image" src="https://github.com/user-attachments/assets/6ca7fa7e-3843-4a06-bd82-01ecf06ef0cf" />
<img width="984" height="484" alt="image" src="https://github.com/user-attachments/assets/64e51d0c-ecd1-49b5-9656-c018b59c8936" />
<img width="784" height="384" alt="image" src="https://github.com/user-attachments/assets/07d2708f-7cd9-4b9d-839f-b0d69435da58" />


### 4. Results & Insights  
- **Sweetness** and **Weight** were key drivers of quality classification  
- **SVC** outperformed other models, showing robustness across splits  
- Logistic Regression underperformed, highlighting non-linear relationships in the data  
- KNN and Random Forest also performed well, close to SVC  

---

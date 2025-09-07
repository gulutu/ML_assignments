# Astronomical Object Classification 🌌  

## 📌 Overview  
This project applies supervised machine learning to classify astronomical objects into three categories: **galaxies, stars, and quasars (QSOs)**.  

The analysis covers the entire pipeline:  
- Data exploration and cleaning  
- Feature engineering and preprocessing  
- Model training and hyperparameter tuning  
- Performance evaluation using multiple metrics  

---

## 📂 Dataset  
- **Training set**: 80,000 samples, 18 columns  
- **Test set**: 20,000 samples, 17 columns (no target)  
- **Target variable**: `class` (GALAXY, STAR, QSO)  

### Selected features after cleaning:  
- Photometric filters: `u`, `g`, `r`, `i`, `z`  
- `redshift`  
- Metadata features with low predictive value (e.g. IDs, coordinates) were dropped  

---

## 🛠️ Skills & Tools Demonstrated  
- **Python**: pandas, NumPy, matplotlib, seaborn  
- **Machine Learning**: scikit-learn (SVC, Logistic Regression, Random Forest, KNN)  
- **EDA**: histograms, boxplots, heatmaps, pairplots  
- **Preprocessing**: handling missing data, feature selection, scaling  
- **Model Evaluation**: accuracy, F1-score, confusion matrices, classification reports  
- **Hyperparameter Tuning**: RandomizedSearchCV  
---

## 🔎 Analysis Workflow  

### 1. Data Exploration & Cleaning  
- Found missing values and extreme values (`-9999`) in `u`, `g`, and `z` filters → handled as NaNs and removed  
- Dropped ID columns and other metadata (`obj_ID`, `spec_obj_ID`, `fiber_ID`, `rerun_ID`) as they had no predictive value  
- Identified strong correlations between some filters (`i-z = 0.97`, `r-i = 0.96`)  
- Noted **class imbalance**:  
  - GALAXY ~59.5%  
  - STAR ~21.6%  
  - QSO ~18.9%
  <img width="561" height="473" alt="image" src="https://github.com/user-attachments/assets/68a7757e-2429-44e4-9f31-357645744a6b" />
<img width="561" height="473" alt="image" src="https://github.com/user-attachments/assets/fa157de1-859d-472e-9d7f-ae4b674ee426" />


### 2. Exploratory Data Analysis (EDA)  
- Histograms and boxplots of filters and redshift  
- Countplot of class distribution  
- Correlation heatmaps of numerical features  
- Pairplots of selected features (e.g., filters vs. redshift, colored by class)  
- Key observations:  
  - **Redshift** separates classes: STARs cluster near 0, GALAXY peaks below 1, QSOs spread higher (up to >3.5)  
  - **Photometric filters** show separation, especially in `g` and `r` bands
<img width="1289" height="1184" alt="image" src="https://github.com/user-attachments/assets/c3c0c388-a8c7-42ec-b34a-c8dc70ef9e9c" />
<img width="1603" height="1526" alt="image" src="https://github.com/user-attachments/assets/8c531aea-8bd3-4e94-a15e-dacb7130e940" />


### 3. Preprocessing  
- Standardized numerical features with `StandardScaler`  
- Split data into training and validation sets  

### 4. Modeling & Hyperparameter Tuning  
Tested multiple models with hyperparameter tuning (RandomizedSearchCV):  
- **Support Vector Classifier (SVC, RBF kernel)**  
- **Random Forest Classifier**  
- **K-Nearest Neighbors (KNN)**  
- **Logistic Regression**  

### 5. Evaluation  
- Metrics: accuracy, F1-score (macro & weighted), confusion matrix, classification report  
- Results showed:  
  - **SVC** and **Random Forest** achieved the best performance  
  - Logistic Regression underperformed (linear decision boundaries insufficient)  
  - KNN performed reasonably well but was sensitive to scaling and choice of k  
<img width="917" height="584" alt="image" src="https://github.com/user-attachments/assets/6089b276-dba1-443d-a58a-b2a9bea43b89" />
<img width="583" height="457" alt="image" src="https://github.com/user-attachments/assets/c3f56fea-06b2-4aee-933c-5413c98784c5" />
<img width="584" height="384" alt="image" src="https://github.com/user-attachments/assets/a754d5d1-b64c-42e4-aab9-8cf156ec4cf0" />
<img width="583" height="457" alt="image" src="https://github.com/user-attachments/assets/94598eb1-e0de-4ce4-bcfa-0f63ed1d09cb" />
<img width="584" height="383" alt="image" src="https://github.com/user-attachments/assets/08dcb9cd-14da-47cc-b0f0-80809b66bba5" />
<img width="784" height="484" alt="image" src="https://github.com/user-attachments/assets/b90827ae-103f-4963-8924-4f3bdbd3ed91" />
<img width="583" height="457" alt="image" src="https://github.com/user-attachments/assets/8ba1d8c9-6a5e-4548-9f19-67cb082a742e" />
<img width="584" height="383" alt="image" src="https://github.com/user-attachments/assets/e3f81c20-c5c7-402d-99b7-70ff4a4ac3fd" />
<img width="583" height="457" alt="image" src="https://github.com/user-attachments/assets/d8bcfe7f-3333-4006-8462-a96858d77f5e" />
<img width="584" height="384" alt="image" src="https://github.com/user-attachments/assets/ac1ea187-3581-49ca-807c-b8a2796a5aa2" />
<img width="784" height="484" alt="image" src="https://github.com/user-attachments/assets/76ff10e3-ee4f-4711-bf70-522c5d7183c3" />

---

## 📊 Key Results & Insights  
- **Data cleaning** (removing outliers and IDs) improved model performance  
- **Scaling** was crucial for SVC and KNN to converge properly  
- **Random Forest** handled nonlinear patterns and feature correlations well  
- **SVC** delivered the strongest overall classification performance  
- The class imbalance slightly reduced recall for the minority classes (QSO, STAR), but models still generalized well  



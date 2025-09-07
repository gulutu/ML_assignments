# Medical Data Classification with Supervised Machine Learning 🩺  

## 📌 Overview  
This project builds a **supervised machine learning pipeline** to classify fetal health based on cardiotocography (CTG) measurements. The dataset contains physiological signals used in prenatal care.  

The focus of the project was to:  
- Perform **data preprocessing** (exploration, cleaning, scaling, balancing)  
- Implement a **train/test split** that preserves class distribution  
- Train and evaluate **linear classifiers** (Perceptron, Adaline, Logistic Regression) from `mlxtend`  
- Investigate how **dataset size** and **training time (epochs)** influence model performance  
- Visualize and compare classification results  

This assignment highlights both **core ML principles** (bias/variance tradeoff, linear separability, scaling) and the ability to implement pipelines without relying on scikit-learn’s high-level abstractions.  

---

## 📂 Dataset  
- **Source**: `fetal_health.csv` (1290 samples, 8 features, 1 target)  
- **Target variable**: `fetal_health` (binary: normal vs. abnormal)  
- **Features include**:  
  - Baseline heart rate value  
  - Accelerations  
  - Short- and long-term variability measures  
  - Histogram features  

---

## 🛠️ Skills & Tools Demonstrated  
- **Python**: pandas, NumPy, matplotlib, seaborn, mlxtend  
- **ML Fundamentals**: train/test split, scaling, class imbalance handling  
- **Model Training**: Perceptron, Adaline, Logistic Regression  
- **Evaluation**: accuracy calculation, visualization with heatmaps  

---

## 🔎 Analysis Workflow  

### Part 1 – Data Exploration  
- Loaded and inspected the dataset  
- Verified **no missing values**  
- Visualized feature distributions (e.g., baseline value ~ normal distribution, accelerations skewed to zero)  
- Identified class imbalance in `fetal_health`
<img width="540" height="393" alt="image" src="https://github.com/user-attachments/assets/2ea6ed00-963a-4fd3-944d-47981e1f359f" />
<img width="540" height="393" alt="image" src="https://github.com/user-attachments/assets/84b46bf4-dd0a-4178-8c44-75b26dcaa567" />
<img width="540" height="393" alt="image" src="https://github.com/user-attachments/assets/9779c70f-bfd2-436b-b9cb-8868e513d8b1" />
<img width="1189" height="989" alt="image" src="https://github.com/user-attachments/assets/b542c00b-6321-4ee5-9b4a-32a126721b06" />

### Part 2 – Train/Test Split  
- Stratified sampling by class to preserve distribution  
- Split into training (~967 samples) and test (~323 samples)  
- Converted DataFrames to NumPy arrays and shuffled training data  
- Resulting class distribution: ~64% class 0, ~36% class 1 across train/test  

### Part 3 – Data Scaling  
- Standardized features (mean=0, std=1) using training set statistics  
- Confirmed successful scaling with summary stats and violin plots  
- Prevented **data leakage** by applying scaling parameters from training set to test set  
<img width="1189" height="790" alt="image" src="https://github.com/user-attachments/assets/7fc474de-39f3-40d7-8f0c-9a62bc6a68f5" />

### Part 4 – Model Training & Evaluation  
- Implemented models using `mlxtend`:  
  - **Perceptron**  
  - **Adaline (Adaptive Linear Neuron)**  
  - **Logistic Regression**  
- Trained models on progressively larger dataset sizes (50 → 700 samples)  
- Evaluated across multiple epochs (2 → 97, step size 5)  
- Stored results in a 3D NumPy array: `(classifier, dataset_size, epochs)`  
- Calculated accuracy manually (`np.mean(y_true == y_pred)`)  

### Part 5 – Results & Visualization  
- Generated heatmaps of **accuracy vs. dataset size vs. epochs** for all classifiers  
- Observed that:  
  - Accuracy increased with **larger datasets**  
  - More epochs improved performance up to a plateau, after which gains diminished  
  - Logistic Regression generally outperformed Perceptron and Adaline  
- Highlighted the importance of **scaling** for convergence  
<img width="1769" height="490" alt="image" src="https://github.com/user-attachments/assets/611fdbc7-e5a3-4ed5-9b1c-d624ca155a48" />
<img width="2989" height="2989" alt="image" src="https://github.com/user-attachments/assets/de1a57fd-4c44-4ed8-be14-d5854bf06862" />

---


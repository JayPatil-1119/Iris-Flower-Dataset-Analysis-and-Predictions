# 🌸 Iris Flower Classification - Data Analysis & Prediction

## 📌 Project Overview
This project focuses on **Exploratory Data Analysis (EDA)** and **Machine Learning modeling** using the famous **Iris dataset**. The goal is to classify iris flowers into three species:
- Setosa
- Versicolor
- Virginica

The project demonstrates the complete workflow from **data preprocessing → visualization → model building → evaluation → optimization**.

---

## 📊 Dataset Information
- Source: Scikit-learn built-in dataset
- Total Records: 150
- Features:
  - Sepal Length
  - Sepal Width
  - Petal Length
  - Petal Width
- Target Classes:
  - 0 → Setosa  
  - 1 → Versicolor  
  - 2 → Virginica  

✔ The dataset is **balanced** with 50 samples per class :contentReference[oaicite:0]{index=0}  

---

## 🔍 Exploratory Data Analysis (EDA)
- Checked dataset structure using `.info()` and `.describe()`
- Verified **no missing values**
- Identified **duplicate records**
- Analyzed class distribution
- Observed:
  - Petal length & width have strong correlation with target
  - Sepal width shows negative correlation

### 📈 Visualizations Used:
- Pairplot (feature relationships)
- Heatmap (correlation matrix)
- Distribution plots

---

## ⚙️ Model Building

### 🔹 Algorithm Used:
- Decision Tree Classifier

### 🔹 Train-Test Split:
- 80% Training
- 20% Testing

---

## 📊 Model Evaluation

### 🔹 Initial Model Performance:
- Training Accuracy: **100%**
- Testing Accuracy: **93.33%**

### 🔹 Metrics:
- Confusion Matrix
- Precision, Recall, F1-score

✔ Model shows slight overfitting due to perfect training score :contentReference[oaicite:1]{index=1}  

---

## 🌳 Feature Importance
| Feature              | Importance |
|---------------------|-----------|
| Petal Width         | Highest   |
| Petal Length        | Moderate  |
| Sepal Width         | Low       |
| Sepal Length        | Negligible|

---

## 🔧 Model Optimization (Pruning)

To reduce overfitting:
- Applied **GridSearchCV**
- Tuned parameters:
  - `max_depth`
  - `min_samples_split`

### 🔹 After Optimization:
- Training Accuracy: **96.67%**
- Testing Accuracy: **93.33%**

✔ Model became more generalized and less complex :contentReference[oaicite:2]{index=2}  

---

## 🌲 Decision Tree Insights
- Tree depth reduced after pruning
- Model relies heavily on:
  - Petal length
  - Petal width

---

## 📦 Model Saving
The trained model is saved using pickle:

```python
import pickle
with open("model.pkl","wb") as f:
    pickle.dump(model,f)

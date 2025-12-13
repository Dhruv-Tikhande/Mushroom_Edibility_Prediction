# 🍄 Mushroom Edibility Prediction

### Machine Learning Classification Project

**Predict whether a mushroom is *edible* or *poisonous* using Random Forest.**

---

## 🚀 Project Overview

This project builds a machine-learning classifier to predict mushroom edibility based on physical characteristics such as:

* Cap diameter
* Stem height & stem width
* Cap, stem, and gill colors
* Bruising/bleeding behavior
* Habitat & season

We follow a complete ML pipeline including **EDA**, **data cleaning**, **encoding**, **model training**, **evaluation**, **feature importance analysis**, and **model saving**.

📌 **Final Model Accuracy:** **99.75% (Random Forest)**

---

## 📁 Dataset Summary

* Total rows: **61,069**
* Original columns: **21**
* After removing high-missing columns: **13 usable features**

### Target Column: `class`

* `e` → edible
* `p` → poisonous

---

## 🔍 Steps in the Project

### **1️⃣ Data Cleaning**

* Analyzed missing values
* Dropped columns with extremely high missing values (>40%)
* Kept clean and meaningful features
* Final data shape: **61,069 × 13**

---

### **2️⃣ Exploratory Data Analysis (EDA)**

Performed:

* Missing value visualization
* Histograms of numeric features
* Boxplots for outlier detection
* Category counts of categorical features
* Class distribution check

📝 Observations:

* Numeric features are right-skewed
* Natural outliers exist due to mushroom diversity
* Data is moderately balanced between edible and poisonous

---

### **3️⃣ Preprocessing**

* Used **OneHotEncoder** for categorical columns
* Retained numeric columns
* Final encoded feature matrix → **61,069 × 72**

---

### **4️⃣ Train/Test Split**

* 80% training, 20% testing
* `stratify=y` to maintain class ratio

---

### **5️⃣ Model Training**

#### **Decision Tree (Baseline)**

* Accuracy: **98.94%**
* Slight overfitting

#### **Random Forest (Final Model)**

* Accuracy: **99.75%**
* Generalizes extremely well
* Best-performing model

---

## 🧠 Feature Importance (Top Insights)

The Random Forest model identified the following as the most influential features:

### **1. Numeric features dominate**

* **stem-width** → highest importance
* **stem-height**
* **cap-diameter**

### **2. Color-based features matter**

* `cap-color`
* `gill-color`
* `stem-color`

### **3. Bruising/Bleeding behavior**

* `does-bruise-or-bleed` plays a key role

### **4. Structural features contribute**

* cap shape
* ring type

### **5. Habitat & season**

* Lower importance but still useful

---

## 💾 Saving the Model

Two important files are saved:

* `mushroom_encoder.pkl`
* `mushroom_model.pkl`

These allow predictions without retraining the model.

---

## 🧪 Example Prediction

```
predict_mushroom_sample({
    'cap-diameter': 5.2,
    'cap-shape': 'x',
    'cap-color': 'n',
    'does-bruise-or-bleed': 't',
    'gill-color': 'w',
    'stem-height': 8.0,
    'stem-width': 1.2,
    'stem-color': 'w',
    'has-ring': 't',
    'ring-type': 'z',
    'habitat': 'd',
    'season': 's'
})
```

Output → **Edible** or **Poisonous**

---

## 📊 Visualizations Included

* Missing value plot
* Histograms (cap-diameter, stem-height, stem-width)
* Boxplots for numeric features
* Categorical bar charts
* Feature importance chart

Each visualization includes clear explanations for easy understanding.

---

## 📌 Final Model Performance

| Model             | Accuracy   | Notes            |
| ----------------- | ---------- | ---------------- |
| Decision Tree     | 98.94%     | Baseline model   |
| **Random Forest** | **99.75%** | Best performance |

---

## 🛠 Technologies Used

* Python
* Pandas
* NumPy
* Scikit-learn
* Matplotlib
* Seaborn

---

## 🙌 Author

**Dhruv** — ML Learner | Data Enthusiast

---

## ⭐ Future Improvements

* Hyperparameter tuning (GridSearchCV)
* Gradient Boosting (XGBoost/LightGBM)
* Deploy using Streamlit
* Add SHAP values for deeper interpretation

---

## 🎯 Summary

This project demonstrates a complete end-to-end machine learning workflow for classification, achieving near-perfect accuracy using a Random Forest model. It includes preprocessing, EDA, modeling, evaluation, interpretation, and model deployment steps.

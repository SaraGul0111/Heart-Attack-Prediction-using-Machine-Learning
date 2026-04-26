# 🫀 Heart Attack Prediction using Machine Learning

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/SaraGul0111/SaraGul/blob/main/Heart_Attack_Prediction.ipynb)
![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-ML-orange?logo=scikit-learn)
![License](https://img.shields.io/badge/License-MIT-green)

---

## 📌 Project Overview

This project aims to predict the likelihood of a heart attack using supervised machine learning techniques. By analyzing clinical and physiological data, five different classification models are trained, evaluated, and tuned to identify the most accurate predictor. The project concludes with a user-friendly input interface that allows real-time risk prediction using the best-performing model.

---

## Objectives

- Perform Exploratory Data Analysis (EDA) on heart health data
- Preprocess the dataset through cleaning, feature selection, and scaling
- Train and evaluate multiple ML classifiers
- Tune hyperparameters using GridSearchCV
- Build an interactive interface for individual patient prediction

---

## 📁 Dataset

The dataset used is `heart.csv`, a widely-used benchmark dataset for cardiac risk prediction.

### Features

| Feature | Description |
|---------|-------------|
| `age` | Age of the patient |
| `sex` | Sex (1 = Male, 0 = Female) |
| `cp` | Chest pain type (0–3) |
| `trestbps` | Resting blood pressure (mm Hg) |
| `chol` | Serum cholesterol (mg/dl) |
| `fbs` | Fasting blood sugar > 120 mg/dl (1 = True) |
| `restecg` | Resting ECG results (0–2) |
| `thalach` | Maximum heart rate achieved |
| `exang` | Exercise-induced angina (1 = Yes) |
| `oldpeak` | ST depression induced by exercise |
| `slope` | Slope of peak exercise ST segment |
| `ca` | Number of major vessels colored by fluoroscopy (0–3) |
| `thal` | Thalassemia type |
| `target` | 1 = Heart attack risk, 0 = No risk |

---

## Tech Stack

| Category | Tools |
|----------|-------|
| Language | Python 3.8+ |
| Data Manipulation | Pandas, NumPy |
| Visualization | Matplotlib, Seaborn |
| Machine Learning | Scikit-Learn |
| Environment | Jupyter Notebook / Google Colab |

---

## Project Workflow

```
Data Loading → EDA & Visualization → Preprocessing → Feature Selection
     → Model Training → Evaluation → Hyperparameter Tuning → Best Model → User Prediction
```

### 1. Exploratory Data Analysis
- Pairplot of continuous features to understand distributions and relationships
- Correlation heatmap to detect multicollinearity among features

### 2. Data Preprocessing
- Removed missing values using `dropna()`
- Removed duplicate rows using `drop_duplicates()`
- Scaled features using `RobustScaler` (robust to outliers)

### 3.  Feature Selection
A custom scoring method combining:
- **Correlation with target** (weight: 0.7)
- **Feature variance** (weight: 0.3)

Top 7 features were selected for model training:
`thalach`, `cp`, `ca`, `oldpeak`, `thal`, `age`, `trestbps`

### 4. Models Trained

| Model | Description |
|-------|-------------|
| Support Vector Machine (SVM) | Linear kernel, C=1 |
| Logistic Regression | Solver: liblinear, max_iter=1000 |
| Decision Tree | Default parameters |
| Random Forest | Ensemble of decision trees |
| Gradient Boosting | 300 estimators, max_depth=1, subsample=0.8 |

### 5. 📈 Evaluation Metrics

Each model is evaluated on:
- **Accuracy**
- **Precision**
- **Recall**
- **F1 Score**

### 6.  Hyperparameter Tuning
GridSearchCV with 5-fold cross-validation was applied to all five models. The best hyperparameters were automatically selected and the models re-evaluated.

### 7.  Best Model Selection
The model with the highest accuracy on the test set was selected automatically. **Gradient Boosting** achieved the highest overall performance.

---

##  User Prediction Interface

After training, the notebook provides an interactive input interface. Users can enter the following clinical values to get a real-time heart attack risk prediction:

```
Enter age:
Enter cp (chest pain type 0-3):
Enter resting blood pressure (mm Hg):
Enter serum cholestoral in mg/dl:
Enter maximum heart rate achieved:
Enter ST depression induced by exercise relative to rest:
Enter number of major vessels colored by flourosopy (0-3):
```

The input is scaled using the same `RobustScaler` and passed to the best tuned model for prediction.

---

##  Getting Started

### Prerequisites

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

### Run Locally

```bash
# Clone the repository
git clone https://github.com/SaraGul0111/SaraGul.git

# Navigate to the folder
cd SaraGul

# Launch Jupyter Notebook
jupyter notebook Heart_Attack_Prediction.ipynb
```

### Run on Google Colab

Click the **Open in Colab** badge at the top of this README to launch the notebook directly in your browser — no installation required.

---

## 📊 Results Summary

| Model | Accuracy |
|-------|----------|
| SVM | ✅ Competitive |
| Logistic Regression | ✅ Competitive |
| Decision Tree | ⚠️ Prone to overfitting |
| Random Forest | ✅ High accuracy |
| **Gradient Boosting** | **Best performing** |

> Note: Exact accuracy values are printed at runtime based on the dataset splits.

---

## 📂 Repository Structure

```
📦 Heart-Attack-Prediction using Machine learning
     📦 Heart-Attack-Prediction using Machine learning
      ┣ 📓 Heart_Attack_Prediction.ipynb   # Main notebook
      ┣ 📄 heart.csv                       # Dataset
README.md                       # Project documentation
```


##  Author

**Sara Gul**  
🔗 [GitHub](https://github.com/SaraGul0111)  

---

## 📃 License

This project is licensed under the [MIT License](LICENSE).

---

> ⭐ If you find this project useful, please consider giving it a star on GitHub!

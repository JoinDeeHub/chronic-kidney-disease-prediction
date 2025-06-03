# Chronic Kidney Disease (CKD) Prediction

This project applies machine learning techniques to predict Chronic Kidney Disease (CKD) using real-world patient data. It is based on medical features such as blood pressure, serum creatinine, hemoglobin, albumin levels, and more. The goal is to assist early diagnosis using automated predictive models.

---

## 📂 Dataset

- Source: [UCI Machine Learning Repository - CKD Dataset](https://archive.ics.uci.edu/ml/datasets/chronic_kidney_disease)
- Samples: 400 patients
- Features: 24 (mixed numerical and categorical)
- Target: `classification` (ckd / notckd)

---

## 🔄 Preprocessing Steps

- Handled missing values represented by `'?'`
- Converted data types using `pandas.to_numeric` where necessary
- Imputed:
  - Numerical columns with **median**
  - Categorical columns with **mode**
- Encoded categorical labels (e.g., `ckd` = 1, `notckd` = 0)
- Feature scaling applied for model training

---

## ⚙️ Machine Learning Models Used

| Model                  | Accuracy | Comments                         |
|-----------------------|----------|----------------------------------|
| Logistic Regression    | ~96%     | Performs well on clean datasets |
| Random Forest Classifier | **98%** ✅ | Highest accuracy and robustness |
| Support Vector Machine | ~95%     | Sensitive to feature scaling    |
| Decision Tree          | ~94%     | Easy to interpret                |

✅ **Final Model Selected:** `RandomForestClassifier`

---

## 📊 Evaluation Metrics

- **Accuracy:** 98%
- **Precision, Recall, F1-Score:** All close to 1.0
- **Confusion Matrix:** Very low false negatives and false positives

---

## 📈 Visualizations

- Correlation heatmap for feature insight
- Boxplots and histograms for univariate analysis
- Pairplot and scatterplots to observe class separation
- ROC Curve for classification evaluation

---

## 🗂️ Files Included

| File/Notebook                         | Purpose                                |
|--------------------------------------|----------------------------------------|
| `chronic_kidney_disease_prediction.ipynb` | Full EDA, preprocessing, model training |
| `chronic_kidney_disease.csv`         | Cleaned dataset (from ARFF)            |
| `random_forest_classification_model.pkl` | Saved model for deployment             |
| `CKD_Model_Deployment_Deepika.ipynb` | Deployment notebook (sample prediction) |

---

## 🚀 Deployment Ready

You can load the `.pkl` model in a Streamlit or Flask app for real-time CKD predictions.

```python
import pickle
with open("random_forest_classification_model.pkl", "rb") as f:
    model = pickle.load(f)

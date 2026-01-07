
# 🚗 Car Insurance Quote Binding Prediction  
**Business-Driven Classification | Cost-Sensitive Modeling | Portfolio Project**

![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)
![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-orange)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![License](https://img.shields.io/badge/License-Academic-lightgrey)

---

## 🔍 Overview
This project addresses a **real-world classification problem**: predicting whether a car insurance quote will convert into a purchased policy (`ISBOUND`).  

Rather than optimizing for accuracy alone, the project is framed around a **business objective**—maximizing advertising profit under asymmetric costs and rewards. This makes the project especially relevant for **industry applications**, where model decisions directly impact revenue.

This project was completed as part of a graduate-level data science course.

---

## 🎯 Business Framing (Why This Matters)
Predictions are assumed to drive a targeted advertising campaign:

- **$1 cost** for each customer targeted (predicted `ISBOUND = 1`)
- **$5.50 revenue** for each successful conversion (true positive)

### 💰 Profit Function
```
Profit = 5.5 × (True Positives) − 1 × (Predicted Positives)
```

This setup forces a realistic trade-off between:
- **False positives** (wasted spend)
- **False negatives** (missed revenue)

➡️ The goal is to **maximize profit**, not accuracy.

---

## 🧠 Modeling Strategy

Two complementary classification approaches were implemented and compared:

### 1️⃣ Logistic Regression (Baseline)
- Interpretable and probability-driven
- Strong baseline for high-dimensional tabular data
- Enables transparent threshold tuning

### 2️⃣ Random Forest (Nonlinear Model)
- Captures interactions and nonlinear effects
- Robust to noise and missing values
- Delivered superior business performance

Both models output calibrated probabilities, which are converted into class predictions using **profit-optimized decision thresholds**.

---

## ⚙️ Data Challenges & Preprocessing
The dataset reflects common industry challenges:

- Heavy **class imbalance**
- Extensive **missing and invalid values**
- Mixed numerical and categorical features

Preprocessing includes:
- systematic data cleaning,
- feature transformation and encoding,
- and consistent training–evaluation pipelines.

All decisions are carefully justified within the notebook.

---

## 📈 Evaluation Methodology

### ROC Analysis
ROC curves are used to compare models across all thresholds, separating model quality from decision rules.

### Business-Optimal Thresholding
Instead of default cutoffs (e.g., 0.5), thresholds are selected to **maximize expected profit**, aligning model behavior with business goals.

---

## 🏆 Results

### 📊 Model Comparison (Illustrative)
| Model              | ROC AUC | Optimal Threshold | Max Profit |
|--------------------|--------:|------------------:|-----------:|
| Logistic Regression|  ~0.63  | Custom            | Lower      |
| Random Forest      |  ~0.89  | Custom            | **Highest**|

📈 *ROC curves and profit-vs-threshold plots are included in the notebook to visualize performance trade-offs.*

**Key Takeaways**
- Random Forest significantly outperformed the baseline in profit terms.
- Default probability thresholds are rarely optimal in business settings.
- Accepting a controlled increase in false positives led to higher overall revenue.

---

## 📂 Repository Structure
```
car-insurance-binding-prediction/
├── notebook/
│   └── DATA6100_Project2_Final.ipynb
├── README.md
```

---

## 🚀 How to Run
```bash
git clone https://github.com/MiladEbrahimiAbyzandi/car-insurance-binding-prediction.git
cd car-insurance-binding-prediction
jupyter notebook
```

---

## 🛠️ Tech Stack
- Python
- pandas, numpy
- scikit-learn
- matplotlib, seaborn
- Jupyter Notebook

---

## ⚠️ Limitations
- Dataset is not included due to access restrictions
- Revenue assumptions are simplified for instructional clarity
- Evaluation is offline (no live deployment)

---

## 🔮 Future Enhancements
- Cost-sensitive and profit-aware learning algorithms
- Gradient boosting (XGBoost / LightGBM)
- Probability calibration and monitoring
- Deployment with real-time inference and tracking

---

## 👤 Author
**Milad Ebrahimi Abyazandi**  
Graduate Student – Data Science  
📍 Canada

---

### ⭐ Portfolio Note
This project demonstrates:
- translating business objectives into ML decision rules,
- handling messy, imbalanced real-world data,
- and evaluating models beyond accuracy using economic metrics.

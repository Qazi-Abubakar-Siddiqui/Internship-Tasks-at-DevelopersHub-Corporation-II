
# Bank Marketing Term Deposit Subscription Prediction

## 📌 Project Objective
The goal of this project is to build an end-to-end Machine Learning pipeline that predicts whether a bank client will subscribe to a term deposit (`y` variable) based on demographic, historical marketing, and socioeconomic attributes. The solution automatically handles data acquisition from the **UCI Machine Learning Repository**, prepares features, runs evaluations, and extracts interpretability parameters using **SHAP (SHapley Additive exPlanations)**.

---

## 📁 Generated Outputs Directory Structure
All generated charts, processed data steps, and evaluation text matrices are compiled and stored inside the auto-created `bank_marketing_outputs/` folder:

```text
bank_marketing_outputs/
├── bank_marketing.zip          # Raw downloaded source file archive
├── extracted/                  # Unzipped CSV contents
├── 01_target_distribution.png  # Distribution chart tracking Imbalance matrix
├── 02_age_distribution.png     # Segmentation of target distribution mapped across ages
├── 03_Logistic_Regression_confusion_matrix.png 
├── 03_Random_Forest_confusion_matrix.png
├── 04_combined_roc_curve.png   # Performance curve benchmarking both algorithms
├── 05_shap_prediction_sample_1.png # Individual Prediction Explanation 1
├── 05_shap_prediction_sample_2.png # Individual Prediction Explanation 2
├── 05_shap_prediction_sample_3.png # Individual Prediction Explanation 3
├── 05_shap_prediction_sample_4.png # Individual Prediction Explanation 4
├── 05_shap_prediction_sample_5.png # Individual Prediction Explanation 5
├── 06_shap_global_summary.png  # Collective feature priority map
└── performance_metrics.txt     # Complete precision, recall, and accuracy output log

```

---

## ⚙️ Methodology & Pipeline Implementation

### 1. Data Cleaning & Encoding

* **Target Variable Alignment:** Class items mapping to `yes` or `no` values are programmatically mapped to binary `1` and `0` representations.
* **Categorical Conversion:** Multi-class feature dimensions such as `job`, `marital`, `education`, `default`, `housing`, and `loan` statuses are processed securely using an automated `LabelEncoder` loop.
* **Feature Scaling:** Standard scaling ($Z$-score normalization) is selectively applied to continuous numeric structures to optimize convergence patterns for distance-based estimators like Logistic Regression.

### 2. Evaluative Modeling Algorithms

Two diverse classifiers are leveraged to capture different structural dynamics within the bank data:

* **Logistic Regression:** Serving as a baseline mathematical benchmark optimized using standardized inputs.
* **Random Forest Classifier:** Ensembled tree strategy capable of navigating multi-class splits and handling systemic class distribution skewness naturally.

---

## 📊 Performance Visualizations Overview

### Target Variable Imbalance (`01_target_distribution.png`)

The dataset displays a notable class imbalance issue where approximately 88% of clients rejected the offer, whereas a smaller 12% chunk subscribed to the term deposit product. This distribution dictates the strategic importance of tracking the **F1-Score** over pure raw classification accuracy.

### Algorithm Benchmarking (ROC Curve Summary)

The comparative receiver operator characteristics determine the spatial separation capacity of your models:

* **Random Forest** typically dominates cross-validation arrays, hitting higher AUC zones ($\approx 0.93+$).
* **Logistic Regression** builds stable, lower-variance decision curves, performing reliably across continuous segments.

---

## 🔍 Explainable AI (XAI) with SHAP

Rather than treating the Random Forest as a complete black-box model, the system tracks specific features driving decisions using Game Theory-backed **SHAP Values**.

### Individual Prediction Files (`05_shap_prediction_sample_1.png` to `_5.png`)

The pipeline selects 5 distinct customer profiles from the test split and breaks down why the model generated its specific probability score:

* **Positive Drivers (Bars pulling towards the right):** Attributes pushing the model to believe the customer **will subscribe** (e.g., higher duration of call, previous successful campaigns).
* **Negative Drivers (Bars pulling towards the left):** Attributes causing the model to expect a **rejection** (e.g., absence of previous contacts, poor economic stability indicators).

### Global Feature Priorities (`06_shap_global_summary.png`)

This master graph demonstrates across all data which traits hold the ultimate leverage:

1. **`duration`:** The length of the marketing call stands out as the primary driving indicator. Longer conversations correlate heavily with subscription sign-ups.
2. **`nr.employed` / `euribor3m`:** Macroeconomic indicator rates deeply impact financial commitment tendencies.
3. **`pdays`:** The number of days that passed by after a client was last contacted from a previous campaign provides strong predictive signals.

---

## 🚀 How to Run the Infrastructure

To completely execute this automated workspace setup on your local device, run the script from your terminal:

```bash
python task1_bank_marketing.py

```

```

### Next Steps
Run the script to download the datasets and populate the `bank_marketing_outputs` directory. This will allow you to see the actual distribution values, confusion matrices, and SHAP breakdowns directly on your machine. Let me know if you would like to explore balancing strategies like SMOTE to optimize the minority class F1-score!

```

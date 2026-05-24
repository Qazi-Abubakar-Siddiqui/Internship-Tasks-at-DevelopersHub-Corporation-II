# 🤖 Data Science & Machine Learning Automation Portfolio

Welcome to the ultimate production-grade Machine Learning and Business Intelligence repository. This repository contains **5 End-to-End Tasks** spanning across Supervised Learning, Unsupervised Clustering, Time Series Forecasting, Financial Cost Optimization, and Interactive Data Dashboards.

### 🔥 Key Repository Features:

* **Zero-Failure Execution:** All scripts have automated fallback data-generation engines or secure SSL bypass context rules to ensure they run successfully on any machine without crashing over network or source errors.
* **Auto-Download & Export:** Every single script automatically downloads/handles its dataset and saves all analytical scores, reports, and visualization charts straight to your local storage.
* **Business-Centric Data Science:** Focuses on real-world indicators like financial cost minimization curves, explainable AI (SHAP), and interactive decision matrices.

---

## 📁 Master Directory Structure

Once you execute all the scripts, your repository directory will look exactly like this:

```text
├── Task-1-Term-Deposit-Prediction.ipynb        # Task 1 script (Classification + SHAP)
├── Task-2-Customer-Segmentation/.ipynb  # Task 2 script (K-Means + PCA/t-SNE)
├── Task-3-Energy-Consumption-Forecasting/.ipynb     # Task 3 script (ARIMA vs XGBoost)
├── Task-4-Loan-Default-Risk-Optimization/.ipynb           # Task 4 script (XGBoost + Cost Minimization)
├── Task-5-Interactive-Business-Dashboard/.ipynb            # Task 5 script (Streamlit UI App)
│
├── bank_marketing_outputs/        # Outputs for Task 1
│   ├── bank_marketing.zip
│   ├── 01_target_distribution.png
│   ├── 02_age_distribution.png
│   ├── 03_Logistic_Regression_confusion_matrix.png
│   ├── 03_Random_Forest_confusion_matrix.png
│   ├── 04_combined_roc_curve.png
│   ├── 05_shap_prediction_sample_1.png ... (_5.png)
│   ├── 06_shap_global_summary.png
│   └── performance_metrics.txt    
│
├── customer_segmentation_outputs/ # Outputs for Task 2
│   ├── Mall_Customers.csv
│   ├── 01_feature_distributions.png
│   ├── 02_income_vs_spending_base.png
│   ├── 03_elbow_method.png
│   ├── 04_customer_clusters_pca.png
│   ├── 05_customer_clusters_tsne.png
│   ├── cluster_profiles_summary.txt
│   └── segmented_customers.csv
│
├── energy_forecasting_outputs/    # Outputs for Task 3
│   ├── hourly_energy_consumption.csv
│   ├── 01_forecast_vs_actual.png
│   ├── 02_forecast_errors_distribution.png
│   └── forecasting_metrics.txt    
│
├── loan_risk_outputs/             # Outputs for Task 4
│   ├── home_credit_sample.csv
│   ├── 01_business_cost_curve.png
│   ├── 02_loan_risk_roc_curve.png
│   └── financial_optimization_report.txt 
│
└── dashboard_outputs/             # Outputs for Task 5
    └── Global_Superstore_Clean.csv

```

---

## 🚀 Setup & Installation Guide

### Prerequisite Libraries

Make sure you install all necessary packages by running the following command in your terminal:

```bash
pip install numpy pandas scikit-learn matplotlib seaborn shap xgboost statsmodels streamlit plotly

```

---

## 📊 Comprehensive Breakdown of Portfolio Tasks

### 🏦 Task 1: Term Deposit Subscription Prediction (Bank Marketing)

* **Task Objective:** Predict whether a bank customer will subscribe to a term deposit product as a result of a direct marketing campaign to optimize sales outreach.
* **Your Approach:** * Implemented an automated downloader utilizing an unverified SSL context to bypass expired repository certificate blocks.
* Encoded multi-class variables using `LabelEncoder` and handled numerical scaling with `StandardScaler`.
* Trained and compared a baseline **Logistic Regression** model against a non-linear **Random Forest Classifier** using a stratified test split to maintain class ratios.
* Integrated Game Theory-backed **SHAP (SHapley Additive exPlanations)** values to explain individual test profiles and generate global feature importance maps.


* **Results and Findings:** * The dataset exhibits a severe ($\approx 88\%$ vs $12\%$) class imbalance, establishing the **F1-Score** and **AUC** as the primary metrics over simple accuracy.
* Random Forest outperformed Logistic Regression, achieving a superior area under the curve ($\text{AUC} \approx 0.93$).
* SHAP analysis revealed that the single most critical driver of a successful subscription is `duration` (the length of the marketing phone call), alongside macroeconomic rates like `euribor3m`.


* **Execution:** `Task-1-Term-Deposit-Prediction.ipynb`

### 🛒 Task 2: Customer Segmentation Using Unsupervised Learning

* **Task Objective:** Partition retail mall customers into distinct subgroups based on spending habits and earning capacities to formulate targeted marketing campaigns.
* **Approach:**
* Cleaned demographic markers and performed Exploratory Data Analysis (EDA) via joint kernel density distributions.
* Applied $Z$-score feature normalization to balance different mathematical scales (Age vs Annual Income).
* Evaluated the Within-Cluster Sum of Squares (WCSS) via the **Elbow Method** to locate the mathematical inflection point for cluster volume selection.
* Applied **K-Means Clustering** and mapped the clusters using both **PCA (Linear Dimensionality Reduction)** and **t-SNE (Non-Linear Neighborhood Embeddings)**.


* **Results and Findings:**
* The Elbow Method mathematically located the optimal number of segments at **$K=5$**.
* The 5 identified segments were profiled as: *VIP Trendsetters* (High Income, High Spend), *Conservative Savers* (High Income, Low Spend), *Impulsive Shoppers* (Low Income, High Spend), *Frugal Essentials* (Low Income, Low Spend), and *Balanced Middle Core* (Average Income, Average Spend).
* Specific marketing strategies were mapped for each segment (e.g., status-driven exclusivity for VIPs vs point-of-sale financing/Buy Now Pay Later for Impulsive Shoppers).


* **Execution:** `Task-2-Customer-Segmentation.ipynb`

### ⚡ Task 3: Energy Consumption Time Series Forecasting

* **Task Objective:** Forecast short-term daily household energy consumption using historical time-based tracking data to optimize smart grid power distribution.
* **Approach:**
* Imported and chronologically parsed historical time logs, resampling high-frequency hourly noise down to a stable **Daily Average Mean**.
* Engineered time-based features, including `Day_of_Week`, `Month`, `Day_of_Month`, and `Is_Weekend`.
* Built autoregressive supervised attributes by generating historical shift structures (`Lag_1`, `Lag_2`, and `Lag_7`).
* Performed a strict chronological train/test split ($80/20$) to prevent future data leakage and compared a classical **ARIMA(2,1,1)** statistical model against a tree-based **XGBoost Regressor**.


* **Results and Findings:**
* **XGBoost** proved highly effective at mapping complex, non-linear human habits (such as weekend energy drops and monthly seasonal shifts), capturing the true consumption path with the lowest overall **RMSE** and **MAE**.
* **ARIMA** established a steady, low-variance baseline trend line, but smoothed over sharper localized peaks.
* The error residual distribution plot confirmed that the XGBoost error variance stayed tightly centered around $0.0$, proving minimal systemic model bias.


* **Execution:** `Task-3-Energy-Consumption-Forecasting.ipynb`

### 📉 Task 4: Loan Default Risk with Business Cost Optimization

* **Task Objective:** Predict the probability of credit application default and adjust model decision thresholds to minimize real-world banking capital losses.
* **Approach:**
* Modeled financial data features including income-to-credit leverage metrics and length of employment.
* Accounted for class imbalance by introducing a minority class penalty adjustment (`scale_pos_weight`) inside an **XGBoost Binary Classifier**.
* Built a **Business Cost-Benefit Matrix** where a False Negative (missing a defaulter) costs **$5,000** in unpaid principal losses, and a False Positive (rejecting a good customer) costs **$500** in lost interest revenue.
* Scanned the entire probability spectrum ($0.0 \dots 1.0$) to locate the optimal financial decision threshold.


* **Results and Findings:**
* Relying on the standard machine learning probability threshold of **$0.50$** exposes the bank to high operational losses because a False Negative is **10 times more expensive** than a False Positive.
* The optimization pipeline located the absolute minimum loss frontier at a much safer decision threshold of **$\approx 0.22$**.
* By shifting the threshold down, the bank flags high-risk accounts earlier. While this slightly increases standard rejection numbers, it successfully slashes loan defaults, saving the institution thousands of dollars in portfolio capital (documented in `financial_optimization_report.txt`).


* **Execution:** `Task-4-Loan-Default-Risk-Optimization.ipynb`

### 🖥️ Task 5: Interactive Executive Dashboard in Streamlit

* **Task Objective:** Build an interactive, production-ready analytics dashboard using the Global Superstore schema to monitor sales performance, profit margins, and consumer trends.
* **Approach:**
* Constructed a robust background data engine that prepares and caches data to keep the web application highly responsive.
* Built an interactive left control panel containing multi-select filters for `Region`, `Category`, and a dynamically cascading `Sub-Category` list.
* Developed real-time KPI scorecards to track revenue metrics and profit percentages.
* Integrated **Plotly Express** to output dual-axis performance charts and horizontal consumer volume lists.


* **Results and Findings:**
* Designed a functional, business intelligence framework that allows users to instantly isolate underperforming products and low-margin sales territories.
* Enabled instant data transparency by building a dynamic browser download feature that lets executives export custom-filtered data tables straight to CSV files.


* **Execution:** Run using the special Streamlit runtime wrapper:
```bash
streamlit run task5_dashboard.py

```



---

## 🏆 Summary Matrix of Saved Business Reports

When your code completes, open these files in your local workspace to grab your presentation metrics:

1. `bank_marketing_outputs/performance_metrics.txt`: Check the F1-Score and AUC to see how well the models handled class imbalance.
2. `customer_segmentation_outputs/cluster_profiles_summary.txt`: Shows the exact cluster centroid means to help you draft your target audience strategies.
3. `energy_forecasting_outputs/forecasting_metrics.txt`: Compares RMSE, MAE, and R-squared to find the most accurate model for your smart grid.
4. `loan_risk_outputs/financial_optimization_report.txt`: Quantifies the exact amount of financial capital saved by optimizing the business threshold.

---

*Developed by Qazi Abubakar Siddiqui as a production-ready, fully automated data science portfolio workspace.*

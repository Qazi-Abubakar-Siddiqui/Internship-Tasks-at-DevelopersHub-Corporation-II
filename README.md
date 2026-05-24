# AI & Machine Learning Projects Repository

Welcome to the **AI & Machine Learning Projects Repository**. This repository contains multiple real-world Machine Learning, Deep Learning, Data Analysis, Time Series Forecasting, Explainable AI, and Business Intelligence projects developed using Python and modern AI/Data Science libraries.

The projects focus on solving practical business problems such as customer targeting, risk prediction, energy forecasting, customer segmentation, and business analytics dashboards.

---

# Repository Structure

```bash
AI-ML-Projects/
│
├── Task-1-Term-Deposit-Prediction/
│   ├── data/
│   ├── notebooks/
│   ├── src/
│   ├── outputs/
│   ├── models/
│   ├── README.md
│   └── requirements.txt
│
├── Task-2-Customer-Segmentation/
│   ├── data/
│   ├── notebooks/
│   ├── src/
│   ├── outputs/
│   ├── models/
│   ├── README.md
│   └── requirements.txt
│
├── Task-3-Energy-Consumption-Forecasting/
│   ├── data/
│   ├── notebooks/
│   ├── src/
│   ├── outputs/
│   ├── models/
│   ├── README.md
│   └── requirements.txt
│
├── Task-4-Loan-Default-Risk-Optimization/
│   ├── data/
│   ├── notebooks/
│   ├── src/
│   ├── outputs/
│   ├── models/
│   ├── README.md
│   └── requirements.txt
│
├── Task-5-Interactive-Business-Dashboard/
│   ├── data/
│   ├── dashboard/
│   ├── outputs/
│   ├── README.md
│   └── requirements.txt
│
├── assets/
├── requirements.txt
└── README.md
```

---

# Technologies Used

## Programming Language

* Python

## Libraries & Frameworks

* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* SHAP
* LIME
* XGBoost
* CatBoost
* Prophet
* Statsmodels
* Streamlit
* Plotly

---

# Installation Guide

## Clone Repository

```bash
git clone https://github.com/your-username/AI-ML-Projects.git
cd AI-ML-Projects
```

---

## Create Virtual Environment

### Windows

```bash
python -m venv venv
venv\Scripts\activate
```

### Linux / Mac

```bash
python3 -m venv venv
source venv/bin/activate
```

---

## Install Dependencies

```bash
pip install -r requirements.txt
```

---

# Task 1: Term Deposit Subscription Prediction

## Problem Statement

Banks conduct marketing campaigns to encourage customers to subscribe to term deposits. However, contacting every customer is costly and inefficient.

The goal of this project is to predict whether a customer will subscribe to a term deposit based on demographic, financial, and campaign-related information.

---

## Objective

* Predict customer subscription behavior
* Improve marketing efficiency
* Reduce unnecessary marketing costs
* Build explainable AI models for business understanding

---

## Dataset

Dataset Used:

* Bank Marketing Dataset
* Source: UCI Machine Learning Repository

### Features Include

* Age
* Job
* Marital Status
* Education
* Balance
* Housing Loan
* Contact Type
* Campaign Duration
* Previous Outcome

### Target Variable

* `y` → Whether customer subscribed (`yes/no`)

---

## Workflow

### 1. Dataset Loading

* Imported dataset using Pandas
* Checked dataset shape and data types

### 2. Data Cleaning & Preprocessing

* Handled missing values
* Encoded categorical variables
* Applied Label Encoding / One-Hot Encoding
* Feature scaling where required

### 3. Exploratory Data Analysis (EDA)

Performed:

* Class distribution analysis
* Correlation heatmaps
* Distribution plots
* Campaign success comparison
* Customer demographic analysis

### Visualizations Included

* Count plots
* Histograms
* Heatmaps
* Box plots
* Pair plots

---

## Model Building

### Models Used

* Logistic Regression
* Random Forest Classifier

### Evaluation Metrics

* Accuracy
* Confusion Matrix
* Precision
* Recall
* F1-Score
* ROC Curve
* ROC-AUC Score

---

## Explainable AI

### SHAP & LIME Explanations

Implemented:

* SHAP Summary Plot
* SHAP Force Plot
* Feature Importance Visualization
* LIME Local Explanations

### Predictions Explained

At least 5 individual predictions were analyzed using:

* SHAP
* LIME

---

## Results & Insights

* Random Forest achieved better predictive performance
* Campaign duration and previous outcomes significantly influenced predictions
* Explainable AI improved model transparency and trust

---

# Task 2: Customer Segmentation Using Unsupervised Learning

## Problem Statement

Businesses need to understand customer behavior to create targeted marketing strategies.

This project clusters customers based on their spending patterns and annual income.

---

## Objective

* Identify customer groups
* Understand purchasing behavior
* Improve targeted marketing
* Increase customer retention

---

## Dataset

Dataset Used:

* Mall Customers Dataset

### Features Include

* Customer ID
* Gender
* Age
* Annual Income
* Spending Score

---

## Workflow

### 1. Data Loading

* Imported dataset
* Inspected missing values and structure

### 2. Data Cleaning

* Removed duplicates
* Checked outliers
* Normalized numerical features

---

## Exploratory Data Analysis (EDA)

Performed:

* Income distribution analysis
* Spending score comparison
* Gender-based analysis
* Correlation analysis

### Visualizations Included

* Scatter plots
* Histograms
* Pair plots
* Heatmaps

---

## Clustering

### Algorithm Used

* K-Means Clustering

### Steps

* Determined optimal clusters using Elbow Method
* Applied clustering algorithm
* Assigned cluster labels

---

## Cluster Visualization

### Techniques Used

* PCA
* t-SNE

### Visual Outputs

* 2D cluster projection plots
* Customer segmentation charts

---

## Marketing Strategies

### Segment-Based Recommendations

#### High Income + High Spending

* Premium memberships
* Luxury product promotions

#### High Income + Low Spending

* Loyalty rewards
* Personalized offers

#### Low Income + High Spending

* Discount campaigns
* Seasonal deals

#### Low Income + Low Spending

* Awareness campaigns
* Budget product recommendations

---

## Results & Insights

* Customers were successfully segmented into meaningful groups
* Spending behavior varied significantly across clusters
* Businesses can improve targeting using segmentation insights

---

# Task 3: Energy Consumption Time Series Forecasting

## Problem Statement

Accurate short-term energy forecasting helps optimize electricity usage and resource planning.

This project predicts household energy consumption using historical time-series data.

---

## Objective

* Forecast future energy consumption
* Compare forecasting algorithms
* Analyze temporal consumption patterns

---

## Dataset

Dataset Used:

* Household Power Consumption Dataset

### Features Include

* Date
* Time
* Global Active Power
* Voltage
* Global Intensity
* Sub-metering values

---

## Workflow

### 1. Data Parsing

* Converted date and time columns
* Created datetime index

### 2. Resampling

* Hourly aggregation
* Daily aggregation

---

## Feature Engineering

Created:

* Hour of day
* Day of week
* Weekday/weekend indicator
* Lag features
* Rolling averages

---

## Exploratory Data Analysis (EDA)

Performed:

* Trend analysis
* Seasonal analysis
* Missing value analysis

### Visualizations Included

* Time series plots
* Rolling mean plots
* Seasonal decomposition
* Correlation analysis

---

## Forecasting Models

### Models Compared

* ARIMA
* Prophet
* XGBoost

---

## Evaluation Metrics

* MAE
* RMSE
* MAPE

---

## Forecast Visualization

Generated:

* Actual vs Forecast plots
* Trend comparison charts
* Prediction interval visualization

---

## Results & Insights

* Prophet captured seasonality effectively
* XGBoost performed well with engineered features
* Forecasting can help optimize household energy planning

---

# Task 4: Loan Default Risk with Business Cost Optimization

## Problem Statement

Financial institutions face major losses due to loan defaults. Traditional prediction systems may not minimize actual business cost.

This project predicts loan default risk while optimizing decision thresholds using business cost analysis.

---

## Objective

* Predict loan defaults
* Minimize financial risk
* Optimize decision thresholds
* Improve business profitability

---

## Dataset

Dataset Used:

* Home Credit Default Risk Dataset

### Features Include

* Customer income
* Employment information
* Credit history
* Loan amount
* Family details

### Target Variable

* Default status

---

## Workflow

### 1. Data Cleaning

* Missing value handling
* Outlier treatment
* Feature encoding

### 2. Data Preprocessing

* Feature scaling
* Feature selection
* Train-test splitting

---

## Exploratory Data Analysis (EDA)

Performed:

* Default rate analysis
* Income comparison
* Correlation analysis
* Risk distribution analysis

### Visualizations Included

* Heatmaps
* Distribution plots
* Bar charts
* Box plots

---

## Model Building

### Models Used

* Logistic Regression
* CatBoost Classifier

---

## Business Cost Optimization

### Cost Definitions

* False Positive Cost
* False Negative Cost

### Threshold Optimization

* Evaluated multiple probability thresholds
* Selected threshold with minimum business cost

---

## Evaluation Metrics

* Confusion Matrix
* F1-Score
* Precision
* Recall
* ROC-AUC Score
* Total Business Cost

---

## Results & Insights

* CatBoost produced strong classification performance
* Optimized threshold reduced business losses
* Cost-sensitive evaluation improved decision-making

---

# Task 5: Interactive Business Dashboard in Streamlit

## Problem Statement

Businesses require interactive dashboards to monitor sales performance and gain actionable insights.

This project develops a Streamlit dashboard for analyzing sales, profit, and customer performance.

---

## Objective

* Build interactive BI dashboard
* Analyze business performance
* Enable dynamic filtering
* Improve decision-making

---

## Dataset

Dataset Used:

* Global Superstore Dataset

### Features Include

* Region
* Category
* Sub-Category
* Sales
* Profit
* Customer Name

---

## Workflow

### 1. Data Cleaning

* Handled missing values
* Converted data types
* Removed duplicates

---

## Dashboard Features

### Filters

* Region
* Category
* Sub-Category

### KPIs Displayed

* Total Sales
* Total Profit
* Top 5 Customers by Sales

---

## Visualizations Included

### Charts

* Bar Charts
* Pie Charts
* Line Charts
* Profit Trend Analysis
* Sales Distribution

---

## Streamlit Features

* Interactive sidebar
* Dynamic filtering
* Responsive layout
* Real-time KPI updates

---

## Running Streamlit Dashboard

```bash
streamlit run app.py
```

---

# Common Features Across All Tasks

Each task includes:

* Problem Statement and Objective
* Dataset Description and Loading
* Data Cleaning and Preprocessing
* Exploratory Data Analysis (EDA)
* Model Building and Evaluation
* Visualizations (Charts, Graphs, Plots)
* Final Conclusions and Insights

---

# Sample Visualizations Included

## Classification Tasks

* Confusion Matrix
* ROC Curve
* Feature Importance
* SHAP Summary Plot

## Clustering Tasks

* PCA Cluster Visualization
* Elbow Method Plot
* t-SNE Projection

## Time Series Tasks

* Forecast Graphs
* Trend Analysis
* Seasonal Patterns

## Dashboard Task

* KPI Cards
* Interactive Charts
* Sales Analysis

---

# Future Improvements

* Deep Learning Integration
* Deployment on Cloud Platforms
* Real-time Prediction APIs
* Automated Model Retraining
* Docker Containerization
* CI/CD Pipeline Integration

---

# Author

## Qazi Abubakar Siddiqui


---

# License

This repository is developed for educational and academic purposes.

---

# Final Conclusion

This repository demonstrates practical implementation of:

* Supervised Learning
* Unsupervised Learning
* Explainable AI
* Time Series Forecasting
* Business Intelligence Dashboards
* Cost Optimization Techniques

The projects provide complete end-to-end workflows starting from raw data preprocessing to model evaluation, visualization, interpretation, and business insights generation.

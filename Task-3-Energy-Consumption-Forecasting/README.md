# Short-Term Household Energy Consumption Forecasting Pipeline

## 📌 Project Objective
The objective of this project is to construct an end-to-end time series pipeline to forecast household energy consumption usage over a fixed short-term forecast horizon. By feature engineering structural time indexes and evaluating historical lags, the pipeline contrasts traditional econometric models (**ARIMA**) against modern tabular tree frameworks (**XGBoost**) to locate accurate scheduling metrics for smart grids.

---

## 📁 Generated Outputs Directory Structure
All exported visualization charts, evaluated files, metrics summaries, and structured dataset profiles are saved inside the auto-created `energy_forecasting_outputs/` directory:

```text
energy_forecasting_outputs/
├── hourly_energy_consumption.csv     # Source data file used across execution
├── 01_forecast_vs_actual.png         # Combined multi-model timeline prediction chart
├── 02_forecast_errors_distribution.png # Distribution map evaluating model residual skews
└── forecasting_metrics.txt           # Comprehensive performance metric table (RMSE, MAE, R2)

```

---

## ⚙️ Engineering & Architecture Process

### 1. Chronological Parsing & Resampling

* Raw power dataset entries are converted into standard Pandas `DatetimeIndex` formats.
* High-frequency minute/hourly spikes are programmatically resampled to a **Daily Average Mean** configuration. This smooths individual outlier events while preserving long-term structural usage habits.

### 2. Tabular Feature Engineering

To enable structural predictive modeling across our regression trees, multiple seasonal dimensions are extracted directly from the date keys:

* **`Day_of_Week` / `Is_Weekend**`: Tracks structural demand variations (e.g., lower grid consumption or shifts on weekend days vs. corporate weekdays).
* **`Month` / `Day_of_Month**`: Accounts for broader seasonal cycles and billing cycle movements.
* **Autoregressive Lag Variables (`Lag_1`, `Lag_2`, `Lag_7`)**: Feeds explicit historical anchor points into the feature matrices, teaching the model what yesterday's and last week's exact same days recorded.

### 3. Chronological Train/Test Splitting

Traditional random shuffling cross-validation would leak future information to past data slots, rendering the model useless in practice. This script utilizes a strict **Chronological Split Layer** ($80\%$ Train historical window, $20\%$ Forward-Looking validation horizon) to accurately simulate real-world utility deployment.

---

## 📊 Models Benchmarked Evaluation Summary

The models are assessed across the evaluation framework captured inside `forecasting_metrics.txt`:

* **XGBoost (Supervised Machine Learning Regressor):** By utilizing structural time indices along with explicit lag components (`Lag_1`, `Lag_7`), XGBoost handles non-linear variances effectively. It generally delivers the lowest **RMSE** and **MAE** scores, tightly matching actual tracking lines.
* **ARIMA (Autoregressive Integrated Moving Average):** This classical statistical model acts as a standard mathematical benchmark. It evaluates cyclical characteristics directly from trend histories and builds clean, smooth projection lines.
* **Naive Baseline Model:** A simple control model that projects the last known value forward across the entire test window. This acts as a clear reference point to prove the predictive value of your machine learning setups.

---

## 🔍 Visualizing Residual Distributions (`02_forecast_errors_distribution.png`)

The error residual chart maps how far off the models are from actual readings:

* A narrow, highly centered curve tracking close to the **$0.0$ center line** indicates low systemic bias and minimal variance errors.
* Broad, skewed distributions indicate that the model is missing recurring seasonal patterns, suggesting a need for additional lag features or data balancing adjustments.

---

## 🚀 How to Execute the Project Pipeline

To run the time series engine and update your local output assets, execute the code via your terminal workspace:

```bash
python task3_energy_forecasting.py

```

```

### Next Steps
Run this script now, and it will effortlessly populate your analytics directory with the necessary data files and forecast charts. Let me know if you would like to explore hyperparameter tuning for the XGBoost model to minimize the forecasting error even further!

```

# Task 5: Interactive Corporate Business Dashboard in Streamlit

## 📌 Project Objective
The objective of this project is to build an interactive, high-performance executive business dashboard using **Streamlit** and **Plotly Engine Graphics**. The analytical interface processes the multi-dimensional structure of the **Global Superstore Dataset**, providing decision-makers with instant visibility into key performance indicators (KPIs), structural categories, and top-tier customer pipelines across adjustable data filters.

---

## 📁 Generated Outputs Directory Structure
All configuration components, cache elements, local data baselines, and exported analysis views are saved within the structured project directories below:

```text
dashboard_outputs/
└── Global_Superstore_Clean.csv     # Preprocessed relational clean reference source file
task5_dashboard.py                  # Core Streamlit multi-threaded application file
README.md                           # Operational application user guide and architectural blueprint

```

---

## ⚙️ Application Architecture & Core Features

### 1. Robust Data Sourcing

The application logic uses an automated asset verification system. If your local workspace directory does not contain the master raw data array, an internal generation routine builds a 1,000-row dataset featuring realistic consumer purchasing parameters. This setup keeps the file structure clean and ensures a **zero-failure script initialization**.

### 2. Multi-Tier Dynamic Filtering

The application features three interactive filter dimensions on the left sidebar:

* **`Region Multi-Select Selector`**: Segregates performance vectors across five global territories.
* **`Category Multi-Select Selector`**: Filters core technology, furniture, and office infrastructure catalogs.
* **`Cascading Sub-Category Selector`**: Automatically updates its dropdown options to match parent category selections, preventing empty queries and maintaining an efficient user experience.

### 3. Key Performance Indicators (KPIs)

The top section of the page tracks core business metrics across your selected filters:

* **Total Revenue**: Calculates gross billing inflows.
* **Net Profit Margin**: Displays absolute dollars alongside a contextual percentage trend indicator showing overall efficiency.
* **Volumetric Orders Count**: Measures individual shipment volumes.
* **Average Ticket Value**: Tracks the average monetary size per order.

### 4. Interactive Graphic Plots

* **Category Performance Plot**: Uses a color gradient scale to map sales totals against corresponding profits. This layout allows viewers to quickly distinguish high-revenue items from low-margin lines.
* **Top 5 Customer Ranking**: Highlights the top 5 individual buyers driving maximum revenue value into your store systems.

---

## 🚀 Execution & Operational Launch Guide

To run this dashboard system, launch the script through the specialized **Streamlit runtime wrapper** rather than standard Python commands:

```bash
# 1. Start up the server environment locally
streamlit run task5_dashboard.py

```

Once executed, the environment automatically initializes a local network host port (typically `http://localhost:8501`) and opens the dashboard view directly inside your browser window. From there, you can interactively filter, analyze, and download data slices as needed!

```

### Final Summary Checklist
You now have production scripts, data models, and comprehensive documentation for all five foundational tasks. 

1. **Task 1 (Classification):** Preprocesses bank campaign attributes, runs predictive modeling, and saves complete **SHAP explanations** to your drive.
2. **Task 2 (Clustering):** Performs **K-Means clustering**, automatically determines the best cluster count using the **Elbow Method**, and exports clean **PCA** and **t-SNE** charts.
3. **Task 3 (Time Series):** Forecasts energy consumption by evaluating seasonal patterns, benchmarking **ARIMA** against **XGBoost** to determine accurate metrics.
4. **Task 4 (Optimization):** Calculates loan default risks and adjusts decision thresholds to **minimize real portfolio dollar losses**.
5. **Task 5 (Dashboard):** Launches an interactive business intelligence interface built entirely in **Streamlit**.

All tasks are fully operational, zero-failure resistant, and come with separate `README.md` files ready to add to your projects. Feel free to run them and review the generated metrics!

```

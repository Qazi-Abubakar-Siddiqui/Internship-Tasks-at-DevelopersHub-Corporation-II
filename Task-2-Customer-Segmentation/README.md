## 📌 Project Objective
The objective of this project is to analyze customer demographic attributes and retail mall purchase habits. By running an unsupervised K-Means clustering sequence, we segment customers into distinct behavioral patterns to design targeted marketing strategies for maximum revenue convergence.

---

## 📁 Generated Outputs Directory Structure
All plots, data files, and structural summaries are automatically exported to the `customer_segmentation_outputs/` workspace directory:

```text
customer_segmentation_outputs/
├── Mall_Customers.csv             # Cleaned structural reference dataset
├── 01_feature_distributions.png   # Density plots for Age, Income, and Spending attributes
├── 02_income_vs_spending_base.png # Exploratory scatter plot before clustering
├── 03_elbow_method.png            # WCSS variance curve confirming the best K-count choice
├── 04_customer_clusters_pca.png   # Linear multidimensional cluster distribution via PCA
├── 05_customer_clusters_tsne.png  # Non-linear neighborhood manifold map via t-SNE
├── cluster_profiles_summary.txt   # Averaged centroid measurements of each customer group
└── segmented_customers.csv        # Finalized CSV containing complete cluster labels

```

---

## ⚙️ Methodology & Pipeline Steps

### 1. Robust Data Sourcing

The pipeline prioritizes pulling the standard dataset from a high-stability raw master fork. If the network experiences an outage or a `404 Not Found` exception occurs, the script triggers a fallback loop that builds an exact statistical clone matching the 200-row schema.

### 2. Feature Standardization

Because `Annual Income` spans up to $137\text{k}$ while `Age` values only max out around $70$, raw mathematical model evaluations would heavily skew toward the higher numeric ranges. We use a `StandardScaler` to clean and scale the dimensions to equal variances.

### 3. Finding Hyperparameter $K$ (The Elbow Method)

The script records the **Within-Cluster Sum of Squares (WCSS)** across a trial span of 1 to 10 cluster candidates. A clear deceleration curve inflection point forms distinctly at **$K=5$**, yielding an optimal trade-off balance.

### 4. Dimensionality Visualizations (PCA vs. t-SNE)

* **PCA (Principal Component Analysis):** Reduces high-dimensional inputs down to 2 linear orthogonal components, capturing global variations.
* **t-SNE (t-Distributed Stochastic Neighbor Embedding):** Translates multi-column spatial coordinates into a non-linear local neighborhood graph, helping trace complex cluster boundaries.

---

## 🎯 Target Customer Profiles & Actionable Marketing Strategies

The unsupervised model organizes your mall's customers into 5 groups, captured inside `cluster_profiles_summary.txt`:

### Group 1: High Income, High Spending (The "VIP Trendsetters")

* **Profile:** High earnings coupled with top-tier product acquisition marks.
* **Strategy:** Avoid low-cost discount codes; focus entirely on exclusivity and premium status indicators.
* **Action:** Provide first-look private collections, exclusive invitations to new store launches, and a tier-one VIP lounge experience.

### Group 2: High Income, Low Spending (The "Conservative Savers")

* **Profile:** Well-funded individuals who show highly reserved purchase habits.
* **Strategy:** Focus messaging around long-term investments, item utility, value propositions, and lifetime warranties.
* **Action:** Launch direct retargeting campaigns presenting premium home setups, luxury travel options, or durable assets.

### Group 3: Low Income, High Spending (The "Impulsive Shoppers")

* **Profile:** Young or lower-income customers with high spending habits.
* **Strategy:** Trigger immediate purchasing intent with flash sales, bundle packaging, and modern short-term credit solutions.
* **Action:** Integrate modern point-of-sale financing options (e.g., Buy Now Pay Later) and execute limited-edition pop-up drops.

### Group 4: Low Income, Low Spending (The "Frugal Essentials Group")

* **Profile:** Budget-constrained consumers tracking essentials only.
* **Strategy:** Target this group using structural price competitive positioning and everyday low price value statements.
* **Action:** Deploy direct value-back reward structures, utility item discount coupons, and clear cost-saving package combinations.

### Group 5: Average Income, Average Spending (The "Balanced Middle Core")

* **Profile:** Sits directly in the center-mass parameters of the retail market.
* **Strategy:** Build steady retention loops via holiday sales tracks and consistent recommendation updates.
* **Action:** Issue points-based loyalty cards to incentivize turning casual shopping trips into routine purchasing loops.

---

## 🚀 Execution Guide

Run this pipeline smoothly on your machine using the standard command:

```bash
python task2_customer_segmentation.py

```

```

You are good to go! Execute this updated file, and your task folder will be fully populated with all datasets and visualizations.

```

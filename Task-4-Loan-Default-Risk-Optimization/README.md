# Loan Default Risk Analysis with Business Cost Optimization

## 📌 Project Objective
The objective of this project is to construct a predictive framework that estimates the probability of loan default while explicitly optimizing credit risk decision cut-offs based on financial cost-benefit equations. By integrating standard banking operational metrics, the pipeline moves beyond abstract accuracy parameters to find the optimal decision boundary that minimizes financial loss for the institution.

---

## 📁 Generated Outputs Directory Structure
All data layers, optimization text logs, performance profiles, and structural evaluation charts are systematically exported to the `loan_risk_outputs/` directory:

```text
loan_risk_outputs/
├── home_credit_sample.csv          # Preprocessed structural credit reference dataset
├── 01_business_cost_curve.png      # Cost minimization curve plotting risk threshold tolerances
├── 02_loan_risk_roc_curve.png      # ROC validation curve benchmarking model discrimination power
└── financial_optimization_report.txt # Operational summary containing saved capital equations

```

---

## ⚙️ Financial Feature Engineering & Methodology

### 1. Risk-Driven Ratios

Raw credit balances alone do not tell the whole story. The pipeline engineers two key financial health ratios:

* **`CREDIT_INCOME_RATIO`**: Measures a borrower's total debt relative to their gross income profile. High values indicate over-leverage.
* **`ANNUITY_INCOME_RATIO`**: Tracks monthly payment obligations against monthly cash flow. This serves as a strong indicator of immediate payment distress risks.

### 2. Imbalanced Class Calibration

Loan default datasets are inherently imbalanced (typically $\approx 8\text{--}9\%$ default rates). A standard model might achieve high accuracy simply by predicting that everyone will pay on time, which fails to protect bank capital. The model configures an active `scale_pos_weight` multiplier within **XGBoost** to correctly penalize errors on the minority default class.

---

## 💵 The Business Cost Matrix Equation

Traditional machine learning assumes that missing a default event is mathematically identical to turning away a reliable borrower. In corporate banking, this assumption is completely flawed. We define a realistic financial impact matrix:

* **False Negative (FN) Cost = $5,000**: The model predicts a client is "Safe", but they default. The bank loses the unpaid loan principal.
* **False Positive (FP) Cost = $500**: The model flags a good client as a "Risk", leading to a rejection. The bank loses out on potential interest revenue.

The model iterates through 100 possible probability cutoff parameters to compute the **Total Portfolio Operational Cost**:

$$\text{Total Business Cost} = (\text{FN} \times \$5,000) + (\text{FP} \times \$500)$$

---

## 📊 Performance Analysis Insights

### The Cost Optimization Frontier (`01_business_cost_curve.png`)

* A standard machine learning model defaults to a **$0.50$ threshold probability cut-off**. However, because a False Negative is **10 times more expensive** than a False Positive, the standard model exposes the bank to substantial financial losses by approving risky loans.
* The optimization matrix automatically pushes the decision boundary lower (typically around **$0.20\text{--}0.30$** depending on asset distributions).
* By actively lowering this threshold, the bank flags higher-risk accounts sooner. While this slightly increases the rejection rate of good customers, it sharply cuts down on catastrophic principal defaults, saving the institution substantial amounts of capital.

---

## 🚀 How to Run the Infrastructure

To completely execute this automated workspace setup on your local device, run the script from your terminal:

```bash
python task4_credit_risk.py

```

```

All files will compile perfectly inside your workspace, with your charts and cost comparisons ready for inspection!

```

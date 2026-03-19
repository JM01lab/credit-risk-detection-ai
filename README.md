# 🏦 Credit Risk Detection with Ethical AI
### An End-to-End Machine Learning Project on IBM watsonx.ai Studio



![Python](https://img.shields.io/badge/Python-3.9-blue) ![IBM Watson](https://img.shields.io/badge/IBM-Watson%20Studio-blue) ![XGBoost](https://img.shields.io/badge/Algorithm-XGBoost-green) ![ROC AUC](https://img.shields.io/badge/ROC%20AUC-0.940-brightgreen) ![Fairness](https://img.shields.io/badge/Fairness-100%25-brightgreen) ![License](https://img.shields.io/badge/License-MIT-yellow)



## 📌 Project Overview

This project builds a complete **AI-powered credit risk detection system** that predicts whether a loan applicant is likely to default on their payment — while ensuring the model is **fair, transparent, and explainable**.

The project was built end-to-end on **IBM watsonx.ai Studio (AutoAI)** and evaluated using **Watson OpenScale** against the **5 pillars of ethical AI**.



## 🎯 Business Problem

Banks and financial institutions face a critical challenge: how to evaluate a borrower's creditworthiness **objectively, at scale, and without human bias**?

Traditional credit scoring systems are often:
- Opaque and difficult to explain
- Prone to systemic bias against certain demographic groups
- Inconsistent across different evaluators

This project explores whether a Machine Learning model can do better — and whether it can do so **ethically**.



## 📊 Dataset

| Characteristic | Detail |
|---------------|--------|
| **Source** | [Kaggle — Credit Risk Dataset](https://www.kaggle.com/datasets/laotse/credit-risk-dataset) |
| **Rows** | 1,000 borrower profiles |
| **Columns** | 12 variables |
| **Target variable** | `loan_status` (0 = no risk, 1 = high risk) |
| **Problem type** | Binary Classification |

### Key Variables

| Variable | Description |
|----------|-------------|
| `person_age` | Borrower's age |
| `person_income` | Annual income |
| `person_home_ownership` | Housing status |
| `person_emp_length` | Employment length |
| `loan_intent` | Purpose of the loan |
| `loan_grade` | Loan grade |
| `loan_amnt` | Loan amount requested |
| `loan_int_rate` | Interest rate |
| `loan_percent_income` | Loan-to-income ratio |
| `cb_person_default_on_file` | Default history |
| `cb_person_cred_hist_length` | Credit history length |
| **`loan_status`** | **Target variable (0 or 1)** |



## 🛠️ Tech Stack

| Technology | Purpose |
|------------|---------|
| **IBM watsonx.ai Studio** | ML development environment |
| **AutoAI** | Automated model creation and comparison |
| **XGBoost** | Best performing algorithm |
| **Watson OpenScale** | Ethical evaluation (Fairness & Quality) |
| **IBM Cloud Object Storage** | Data and model storage |
| **Python / Jupyter Notebook** | Exported model code |



## ⚙️ Methodology

The project followed this end-to-end pipeline:

```
1. Data Collection (Kaggle)
        ↓
2. Data Import into IBM Watson Studio
        ↓
3. AutoAI Experiment (Binary Classification)
        ↓
4. Automatic Model Training & Comparison
        ↓
5. Best Model Selection (XGBoost Ensemble)
        ↓
6. Model Deployment (Online API)
        ↓
7. Ethical Evaluation (Watson OpenScale)
        ↓
8. Documentation & Reporting
```



## 🏆 Results

### Best Model: XGBoost with HPO + Feature Engineering + Ensemble

| Metric | Score | Threshold | Status |
|--------|-------|-----------|--------|
| **ROC AUC** | **0.940** | 0.80 | ✅ Excellent |
| **Precision** | **0.95** | 0.75 | ✅ Outstanding |
| **Recall (TPR)** | **0.72** | 0.80 | ⚠️ Below threshold |
| **MCC** | **0.79** | 0.80 | ⚠️ Slight violation |

### Key Takeaways:
- **Precision of 95%**: When the model flags a borrower as high-risk, it is correct 95% of the time
- **ROC AUC of 0.940**: Excellent discrimination between risky and safe profiles
- **Recall of 0.72**: The model misses 28% of truly risky cases — a clearly identified improvement point



## ⚖️ Ethical Analysis

The model was evaluated against the **5 pillars of ethical AI**:

| Pillar | Result | Detail |
|--------|--------|--------|
| ⚖️ **Fairness** | ✅ 100% | No bias detected across age or income groups |
| 🛡️ **Robustness** | ✅ Strong | XGBoost Ensemble with HPO ensures stability |
| 🔍 **Explainability** | ✅ Documented | Controllable features identified for borrowers |
| 👁️ **Transparency** | ✅ Full | Entire process documented in this repository |
| 🔒 **Privacy** | ✅ Preserved | Public dataset used — no real personal data |

### Fairness Details:
- **Disparate Impact Score: 100%** — No bias related to age (18–25 vs 26–60) or income ($0–$30K vs $30K+) was detected
- The model treats every borrower equitably regardless of their demographic profile



## 📁 Repository Structure

```
credit-risk-detection-ai/
│
├── 📓 notebook/
│   └── credit_risk_autoai_model.ipynb    # Exported AutoAI notebook
│
├── 📊 data/
│   └── credit_risk_dataset.csv           # Training dataset (Kaggle)
│
├── 📄 reports/
│   └── Ethical_Analysis_Report_EN.pdf    # Full ethical analysis report
│
├── 🖼️ images/
│   └── autoai_leaderboard.png            # AutoAI pipeline leaderboard
│   └── fairness_100.png                  # Fairness 100% screenshot
│   └── prediction_result.png             # Model prediction result
│   └── quality_metrics.png               # Quality evaluation metrics
│
└── 📝 README.md                          # This file
```



## 🚀 How to Run

### Option 1: Run on IBM Watson Studio (Recommended)
1. Create a free account on [IBM Cloud](https://cloud.ibm.com/registration)
2. Launch **watsonx.ai Studio**
3. Create a new project
4. Import `credit_risk_dataset.csv`
5. Open the exported notebook `credit_risk_autoai_model.ipynb`
6. Run all cells

### Option 2: Run Locally
```bash
# Clone the repository
git clone https://github.com/YOUR_USERNAME/credit-risk-detection-ai.git

# Install dependencies
pip install xgboost scikit-learn pandas numpy matplotlib

# Open the notebook
jupyter notebook notebook/credit_risk_autoai_model.ipynb
```



## 📈 Recommendations for Improvement

1. **Adjust the decision threshold** from 0.5 to 0.4 to improve Recall
2. **Enrich the dataset** with more diverse profiles (10,000+ rows)
3. **Apply SMOTE** to address class imbalance
4. **Re-evaluate Fairness metrics** after each improvement



## 📖 Related Article

Read the full project write-up on Medium:
> **"I Built a Bias-Free AI That Predicts Credit Risk with 94% Accuracy — Here's How"**

*Link: [Add your LinkedIn/Medium article link here]*



## 👤 Author

**Jeancy Joachim Mukaka**
- AWS Community Builder — Developer Tools (March 2026)
- IBM Watson Studio | Machine Learning | AI Ethics
- 🔗 www.linkedin.com/in/jeancy-joachim-mukaka-495411227



## 📜 License

This project is licensed under the MIT License — feel free to use, modify, and share with attribution.

---

## 🙏 Acknowledgements

- [IBM Watson Studio](https://www.ibm.com/cloud/watson-studio) for the ML development platform
- [Kaggle](https://www.kaggle.com/datasets/laotse/credit-risk-dataset) for the Credit Risk Dataset
- [IBM AI Fairness 360](https://aif360.mybluemix.net) for ethical AI frameworks

---

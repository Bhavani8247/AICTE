# AI-Assisted E-Commerce Data Analytics & Customer Churn Prediction

**Participant:** BHavani Ponde
**Internship:** AICTE | IBM SkillsBuild Data Analytics with AI Internship 2026

## Project Overview

This project applies the internship's Masterclass 1–3 workflow to an e-commerce transaction dataset:

1. Data cleaning and validation
2. Exploratory Data Analysis (EDA)
3. Business observations, insights, hypotheses and recommendations
4. Customer-level RFM-style feature creation
5. Leakage-safe future churn target
6. Logistic Regression
7. Churn probability and customer risk levels
8. Business actions

## Dataset

The project uses the **Masterclass 1 Practice Dataset** supplied with the internship materials.

The original workbook contains 2,000 transaction rows and examples of data-quality issues such as inconsistent category/region capitalization, invalid dates, currency-formatted revenue values, missing values, duplicate rows and negative quantities.

The submitted `data/cleaned_ecommerce.csv` is a cleaned analytical version of that source data.

### Cleaning summary

- Raw transaction rows: 2,000
- Duplicate rows detected: 23
- Clean analytical rows: 1,810
- Unique customers in cleaned transactions: 408
- Invalid dates removed: 24
- Negative quantities removed: 41

## Masterclass Alignment

### Masterclass 1 — AI + Data
- Data quality validation
- Cleaning and normalization
- Business questions

### Masterclass 2 — AI Discovers the Story
Five visualizations are included:
- Monthly revenue
- Category revenue
- Customer segments
- Regional revenue
- Top products by profit

The notebook also records observations, insights, hypotheses and recommendations.

### Masterclass 3 — AI Predicts What Happens Next
- One row per customer
- Recency, Frequency and Monetary features
- Leakage-safe historical snapshot
- Logistic Regression
- Accuracy, precision, recall and ROC-AUC
- Confusion matrix
- Customer churn probabilities
- Low / Medium / High risk levels

## Important Churn Definition Note

The supplied Masterclass 3 workbook contains inconsistent classroom instructions: one section defines churn at 90 days, while later sections refer to 180 days. The same workbook also explicitly warns against target leakage and recommends a historical snapshot approach.

Because the supplied transaction data ends on **8 Dec 2026**, a complete 180-day future observation period cannot be constructed from the supplied data.

For this project, the implementation therefore uses:

- Historical feature cutoff: **31 Aug 2026**
- Future observation window: **90 days**
- Churn target: **No purchase during the 90-day future window**

This is documented as a project implementation choice rather than presented as the only possible trainer definition.

## Model Results

Using a stratified 75/25 train-test split with `random_state=42`:

- Accuracy: **77.78%**
- Precision: **81.33%**
- Recall: **88.41%**
- ROC-AUC: **70.24%**

These are the results of this project's actual implementation and should not be confused with sample metric values shown in the training workbook.

## Repository Structure

```text
AICTE_IBM_Data_Analytics_Project_Akshith/
├── Akshith_ECommerce_Churn_Analysis.ipynb
├── Akshith_ProjectReport.docx
├── README.md
├── requirements.txt
├── data/
│   ├── cleaned_ecommerce.csv
│   ├── data_dictionary.csv
│   ├── customer_churn_features.csv
│   └── customer_risk_scores.csv
└── report_assets/
    ├── 01_monthly_revenue.png
    ├── 02_category_revenue.png
    ├── 03_customer_segments.png
    ├── 04_region_revenue.png
    ├── 05_top_product_profit.png
    └── 06_confusion_matrix.png
```

## How to Run

### Local Python

```bash
python -m venv .venv
```

Windows:

```bash
.venv\Scripts\activate
```

macOS/Linux:

```bash
source .venv/bin/activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Open the notebook:

```bash
jupyter notebook Akshith_ECommerce_Churn_Analysis.ipynb
```

### Google Colab

1. Upload the notebook.
2. Upload the `data/cleaned_ecommerce.csv` file.
3. Create a `data` folder in the Colab working directory or update `DATA_PATH`.
4. Run all cells from top to bottom.

## Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- Jupyter Notebook / Google Colab
- Logistic Regression

## Key Business Findings

- Electronics is the largest revenue category in the cleaned dataset.
- Pune has the highest regional revenue in the cleaned dataset.
- Repeat customers form a substantial portion of the customer base.
- Monthly revenue varies considerably across 2026.
- Laptop is the highest-profit named product in the cleaned dataset.

## Disclaimer

This is an academic internship project. The churn model is a baseline predictive model intended for learning and demonstration. It should not be treated as a production decision system without further validation, monitoring, and business review.

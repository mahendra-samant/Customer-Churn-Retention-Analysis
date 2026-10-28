# Customer Churn & Retention Analysis

A business-focused exploratory data analysis project that examines customer churn, retention patterns, subscription behaviour, and recurring monthly revenue exposure using the IBM Telco Customer Churn dataset.

The project combines **Python-based analytics with SQLite** to demonstrate a practical Data Analyst workflow from raw customer data to business recommendations.

## Business Objective

The objective is to understand:

- Which customer segments have elevated churn?
- At what stage of the customer lifecycle is churn concentrated?
- Which contract, service and payment patterns are associated with churn?
- Which churned customers represent the greatest recurring-revenue exposure?
- What operational actions could support customer retention?

This project focuses on descriptive and diagnostic analytics rather than building a machine-learning churn prediction model.

## Key Results

The cleaned dataset contains **7,043 customers**:

| KPI | Result |
|---|---:|
| Total customers | 7,043 |
| Churned customers | 1,869 |
| Retained customers | 5,174 |
| Churn rate | 26.5% |
| Retention rate | 73.5% |
| Current monthly charges | $456,116.60 |
| Monthly charges attached to churned customers | $139,130.85 |
| Average monthly charge | $64.76 |
| Average tenure | 32.4 months |

### Important findings

- Customers with **0–6 months of tenure** have a 52.9% churn rate, compared with 9.5% for customers with 49–72 months of tenure.
- **Month-to-month customers** have a 42.7% churn rate, compared with 11.3% for one-year contracts and 2.8% for two-year contracts.
- Month-to-month churn accounts for approximately **$120.8K of the $139.1K monthly charges at risk**.
- **Fiber-optic** customers have a 41.9% churn rate in this dataset.
- Customers using **electronic check** have a 45.3% churn rate, the highest among payment methods.
- Customer-reported churn reasons include competitive offers, support/service experience, network reliability, product dissatisfaction and pricing concerns.
- The provided dataset contains only one unique state, so state-level churn comparisons are not meaningful and are intentionally not presented as a business finding.

> Churn rates and segment differences are observational associations. They should not be interpreted as proof that a contract, service, or payment method directly causes churn.

## Analytical Workflow

```text
Raw CSV
   ↓
Data Quality Audit
   ↓
Data Cleaning
   ↓
SQLite Analytical Layer
   ↓
Executive KPIs
   ↓
Customer Segmentation
   ↓
Lifecycle & Contract Analysis
   ↓
Service & Payment Analysis
   ↓
Revenue-at-Risk Analysis
   ↓
Churn Reason Analysis
   ↓
SQL Business Queries
   ↓
Business Findings & Recommendations
```

## Analysis Areas

### Customer lifecycle
- Tenure distribution
- Tenure-band churn rates
- Early-lifecycle retention risk

### Contract behaviour
- Contract mix
- Churn rate by contract
- Revenue exposure by contract

### Service engagement
- Internet service
- Online security
- Online backup
- Device protection
- Technical support
- Streaming services
- Service engagement level

### Customer segmentation
- Gender
- Senior-citizen status
- Partner status
- Dependents

### Payment behaviour
- Payment method distribution
- Churn rate by payment method
- Revenue exposure by payment method

### Revenue analysis
- Monthly recurring charges
- Monthly charges attached to churned customers
- Customer-level revenue concentration
- Tenure × contract revenue-risk matrix

### Voice of the customer
- Recorded churn reasons
- Competitive pressure
- Service/support issues
- Product and pricing concerns

### SQL analysis
The cleaned customer table is loaded into SQLite and queried using SQL for business aggregations such as churn by contract and tenure.

## Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- SQLite
- Jupyter Notebook

## Project Structure

```text
Customer-Churn-Retention-Analysis/
│
├── data/
│   └── IBM_Telco_Customer_Churn.csv
│
├── Customer_Churn_Retention_Analysis.ipynb
├── README.md
├── .gitignore
└── churn_analysis.sqlite
```

`churn_analysis.sqlite` is generated automatically by the notebook and should normally remain local rather than being committed to GitHub.

## How to Run

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/Customer-Churn-Retention-Analysis.git
cd Customer-Churn-Retention-Analysis
```

### 2. Install dependencies

```bash
pip install pandas numpy matplotlib seaborn jupyter
```

### 3. Start Jupyter Notebook

```bash
jupyter notebook
```

### 4. Open

```text
Customer_Churn_Retention_Analysis.ipynb
```

Run the notebook from the project root so that the relative dataset path works:

```text
data/IBM_Telco_Customer_Churn.csv
```

## Dataset

The project uses the IBM Telco Customer Churn dataset. The dataset contains customer demographics, subscribed services, contract and payment information, financial measures, churn status, and recorded churn reasons.

The analysis keeps the original customer-level dataset locally in the `data/` directory.

## Limitations

- The dataset represents a customer snapshot rather than a complete longitudinal history.
- Observational relationships do not establish causation.
- The `Churn Score` and `CLTV` fields are source-derived fields and are excluded from explanatory driver analysis.
- Recorded churn reasons represent customer-reported categories in the source data.
- Monthly revenue at risk is the current monthly charge of churned customers, not a lifetime-revenue forecast.
- Marketing activity, discounts, acquisition cost, service-quality measures and competitor pricing are not available.
- The dataset has no useful state-level variation for geographic comparison.

## Future Improvements

Possible extensions include:

- Build an interactive Power BI dashboard
- Add customer cohort analysis if historical snapshots become available
- Test retention experiments using additional business data
- Add marketing and discount history
- Build a separate churn prediction model
- Develop customer lifetime value analysis using richer financial data
- Automate recurring churn reporting

## Author

**Mahendra**

GitHub: `https://github.com/mahendra-samant`

## License

This project is intended for educational and portfolio purposes.

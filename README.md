# Data Analytics with AI Individual Formative Assignment One: Python ETL and Visualisation
## Fraud-analysis (Bank Transaction Analysis) Project by Arphaxad Nguka Owange

## Table of Contents
1. [Project Overview & Goal](#1-project-overview-goal)
2. [Technical Stack](#2-technical-stack)
3. [ETL Pipeline and Transformation Summary](#3-etl-pipeline-and-transformation-summary)
4. [How to Run the Project Locally](#4-how-to-run-the-project-locally)
   
## 1. Project Overview & Goals
This project analyzes synthetic financial transaction data to detect patterns and characteristics of fraudulent activities using Python ETL processes and data visualization techniques.

#### Key Research Questions
1. Q1: Fraud Transactions vs Transaction Amount -Which amount ranges have the highest fraud?
2. Q2: Fraud Transactions vs Geographic Distance -Which geographic locations have the highest fraud?
3. Q3: Can a prediction model for fraud in banking transactions be developed?

## 2. Technical Stack

- **Core Languages:** Python
- **Data Processing (ETL):** Pandas, NumPy, kagglehub
- **Visualisation:** Matplotlib (Basic Plotting), Seaborn (Statistical Visuals/Heatmaps), Scipy, Scikit Learn (Machine Learning) and Streamlit (Advanced Interactive Charts)
- **Version Control:** Git & GitHub

## 3. ETL Pipeline and Transformation Summary
The data used is the [*Transactions Dataset*](https://www.kaggle.com/datasets/ismetsemedov/transactions), containing 7483766 records and 24 attributes. This was reduced to 1000 records and 13 attributes due to lage volume size

For this dataset, we were fortunate to have no missing values, so no imputation was required. Our main transformations focused on engineering new features to support analysis and visualisation.

### Amount_usd
Currencies were converted into one standard currency the USD and plotted in approprite column.

### Amount_tier
The amount_usd was binned into 0-100', '101-200', '201-500', '500+ for easier visualization and reporting

### Categorical Variables Encoding
For machine level predictions the all the categorical values were encoded.

## Key Findings
**Question 1:**

- The extreme outliers in legitimate transactions significantly skew: Fraudulent transaction amounts show less variability. The visualisation suggests that while amount is important, fraud cannot be detected by amount alone - many fraudulent transactions fall within "normal" ranges, while many legitimate transactions are extreme outliers.

**Question 2:**
- For MOST Countries, away-from-home transactions (1) are more frequently fraudulent than at-home transactions (0). Distance from home is NOT equally predictive across countries. Low-risk countries suggest better fraud controls or reporting.

- **Question 3:**

Fraudulent transactions tend to be smaller on average, suggesting fraudsters may test with smaller amounts first. Legitimate transactions have more extreme high-value outliers, which could cause false positives in fraud detection.¶
Correlation with fraud: Amount_usd shows a positive correlation of 0.23 with fraud, indicating higher amounts are somewhat associated with fraud risk.

Business Implication: Cannot use amount alone for fraud detection - high-value legitimate transactions look suspicious, while many fraudulent transactions fall within "normal" ranges. Effective prediction models can be developed - We achieved excellent performance metrics suitable for production deployment. Key fraud indicators identified: Geographic anomalies (distance from home) and Country-specific risk profiles.

Recommendations for Implementation:

Deploy Random Forest model for best balance of precision and recall

## 4. How to Run the Project Locally

### Clone the Repository

```bash
git clone [https://github.com/arphaxad1985t/fraud_analysis]

cd Fraud_analysis
```
### Install Dependencies

You will need a ```requirements.txt``` file listing pandas, numpy, streamlit, etc.
Open your terminal or a Jupyter cell and run:

```bash
pip install -r requirements.txt

**##** **Author**
**###** **Arphaxad Nguka Owange**

**##** **License**
**This project is for educational purposes as part of Data Analytics with AI coursework at the Code Institute.**

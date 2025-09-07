# Customer Churn Analysis with AI Insights

## 📌 Overview
This project analyzes telecom customer churn data.  
The aim is to identify churn drivers, clean the dataset, and prepare for visualization and analysis.  
AI (ChatGPT) was integrated to recommend feature engineering and cleaning approaches.

## 📊 Dataset
- Source: [Telco Customer Churn – Kaggle](https://www.kaggle.com/datasets/blastchar/telco-customer-churn)
- Raw file: `/data/Telco-Customer-Churn.csv`

## 🧠 AI Contribution
- Suggested encoding and cleaning methods
- Recommended new features for churn analysis (e.g., Average Monthly Spend, AutoPayment flag)

## 📂 Project Structure
/data → raw & cleaned datasets
/notebooks → Jupyter notebooks
/reports → PDFs, dashboard screenshots
/docs → AI documentation

## ⚙️ Project Workflow
1. **Data Cleaning & Preprocessing**
   - Handled missing values
   - Encoded categorical variables
   - Engineered features (MonthlyCostPerService, normalized charges)

2. **Exploratory Data Analysis (EDA)**
   - Churn distribution by contract type
   - Impact of tenure and monthly charges on churn
   - Risk segmentation

3. **Dashboard (Power BI)**
   - KPIs: Total Customers, Churned Customers, ChurnRate %, Avg Tenure,Total Monthly Revenue Lost
   - Visuals: Churn Rate By tenure Bucket, Churn rate By Contract Type, Revenue Lost By Gender, Churn Trend Over Tenure

4. **AI-Assisted Insights**
   - Suggested KPIs via ChatGPT
   - Summarized insights into business-friendly language
   - Generated sample stakeholder Q&A

## Key Findings
📌 Customer base is strong (3,168 total), but churn of 214 customers (6.8%) poses a risk to long-term stability.

📌 Contracts matter — 2-year contracts show stronger retention, while 1-year contracts contribute more to churn, highlighting the need for longer-term engagement.

📌 Churn is highest among customers in the 37–48 month tenure range, as well as in the early 0–12 month group, suggesting both onboarding and mid-life cycle retention gaps.

📌 Revenue loss is significant — ~$18.3K monthly, with male churners accounting for a slightly higher share than female churners, creating an opportunity for gender-focused retention strategies.

📌 Churn trend fluctuates heavily in the first 20 months, then stabilizes, pointing to critical early intervention opportunities to reduce future churn.

## 📊 Dashboard
- 📄 File: `reports/churns_dashboard.pbix`
- 📷 Screenshots: `reports/visuals/`

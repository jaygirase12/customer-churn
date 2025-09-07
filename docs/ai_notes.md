**###### \\##AI Documentation**

**######** 

**###### \\## Prompt 1:**Suggest data transformations and encoding methods for customer churn analysis in Python Pandas.
**###### \\## AI Response:**
**1. Drop Unnecessary Columns**
Some columns are identifiers and don’t add predictive value.

df.drop(\['customerID'], axis=1, inplace=True)

**2. Handle Missing Values**
TotalCharges often has blanks → convert to numeric and impute.

df\['TotalCharges'] = pd.to\_numeric(df\['TotalCharges'], errors='coerce')
df\['TotalCharges'].fillna(df\['TotalCharges'].median(), inplace=True)

**3. Encode Target Variable (Churn)**
Convert "Yes"/"No" into binary.

df\['Churn'] = df\['Churn'].str.strip().map({'Yes': 1, 'No': 0})

**4. Encode Categorical Features**
Identify categorical columns:

cat\_cols = df.select\_dtypes(include=\['object']).columns
print(cat\_cols)



**Encoding Methods**

**(a) Binary Columns (Yes/No → 0/1)**

binary\_cols = \['Partner','Dependents','PhoneService','PaperlessBilling']
for col in binary\_cols:

&nbsp;   df\[col] = df\[col].map({'Yes': 1, 'No': 0})



**(b) Nominal Categorical (No Order → One-Hot Encoding)**

For multi-class categorical (e.g., InternetService, PaymentMethod).

df = pd.get\_dummies(df, columns=\['InternetService','PaymentMethod','Contract'], drop\_first=True)



**\*\*###### \\## Prompt 2**:\*\*Suggest 3 new features for churn analysis that I can calculate from this dataset.

**###### \\## AI Response:**
**1. Average Monthly Spend per Tenure**

Why: Long-term customers spending less may be at higher churn risk.
Code:

df\['AvgMonthlySpend'] = df\['TotalCharges'] / (df\['tenure'] + 1)

**2. Total Number of Services Subscribed**

Why: Customers with more bundled services are usually more “sticky” (less likely to churn).
Code (example if you one-hot encoded service columns):



service\_cols = \['PhoneService','MultipleLines\_Yes','OnlineSecurity\_Yes',
&nbsp;               'OnlineBackup\_Yes','DeviceProtection\_Yes','TechSupport\_Yes',
&nbsp;               'StreamingTV\_Yes','StreamingMovies\_Yes']
df\['TotalServices'] = df\[service\_cols].sum(axis=1)



**3. Contract Risk Score**

Why: Month-to-month customers are more likely to churn compared to yearly contracts.
Code:
contract\_map = {'Month-to-month': 1, 'One year': 0.5, 'Two year': 0}
df\['ContractRisk'] = df\['Contract'].map(contract\_map)


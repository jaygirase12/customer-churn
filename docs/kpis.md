**\*\*##KPI\*\***



**\*\*## Prompt 1\*\*:**“I have customer churn dataset with tenure, monthly charges, total charges, and churn flag. Suggest KPIs and DAX formulas for churn analysis.”



**\*\*##AI Response:\*\***

**🔑 KPIs for Churn Analysis**

**1. Total Customers**



How many unique customers are in the dataset.



Total Customers = DISTINCTCOUNT(Churn\[customerID])



**2. Churned Customers**



How many customers have churned.



Churned Customers = CALCULATE(

&nbsp;   DISTINCTCOUNT(Churn\[customerID]),

&nbsp;   Churn\[Churn] = 1

)



**3. Churn Rate (%)**



Percentage of customers that left.



Churn Rate % = 

DIVIDE(

&nbsp;   \[Churned Customers],

&nbsp;   \[Total Customers],

&nbsp;   0

)



**4. Average Tenure of Churned Customers**



Are new or old customers leaving?



Avg Tenure (Churned) = 

CALCULATE(

&nbsp;   AVERAGE(Churn\[tenure]),

&nbsp;   Churn\[Churn] = 1

)



**5. Average Monthly Revenue Lost (Churned Customers)**



How much recurring revenue is lost per churned customer.



Avg Monthly Charges (Churned) = 

CALCULATE(

&nbsp;   AVERAGE(Churn\[MonthlyCharges]),

&nbsp;   Churn\[Churn] = 1

)





If you want total revenue lost:



Total Monthly Revenue Lost = 

CALCULATE(

&nbsp;   SUM(Churn\[MonthlyCharges]),

&nbsp;   Churn\[Churn] = 1

)


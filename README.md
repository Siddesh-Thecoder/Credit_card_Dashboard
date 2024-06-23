# Credit_card_Dashboard
I am excited to share a recent project I completed on Credit Card Transaction and Customer report using Power BI.

𝐏𝐫𝐨𝐣𝐞𝐜𝐭 𝐎𝐛𝐣𝐞𝐜𝐭𝐢𝐯𝐞:
To develop a comprehensive credit card  weekly  dashboard  that provides real-time  insights into key performance metrics and trends, enabling stakeholders to monitor and  analyze credit card operations effectively.

𝐃𝐚𝐭𝐚 𝐈𝐦𝐩𝐨𝐫𝐭𝐢𝐧𝐠 (𝐂𝐒𝐕):
Import data to SQL database
1. Prepare csv file
2. Create tables in SQL
3. import csv file into SQL

𝐃𝐀𝐗 𝐐𝐮𝐞𝐫𝐲 :
AgeGroup = SWITCH(
 TRUE(),
 'public cust_detail'[customer_age] < 30, "20-30",
 'public cust_detail'[customer_age] >= 30 && 'public cust_detail'[customer_age] < 40, "30-40",
 'public cust_detail'[customer_age] >= 40 && 'public cust_detail'[customer_age] < 50, "40-50",
 'public cust_detail'[customer_age] >= 50 && 'public cust_detail'[customer_age] < 60, "50-60",
 'public cust_detail'[customer_age] >= 60, "60+",
 "unknown"
 )

IncomeGroup = SWITCH(
 TRUE(),
 'public cust_detail'[income] < 35000, "Low",
 'public cust_detail'[income] >= 35000 && 'public cust_detail'[income] <70000, "Med",
 'public cust_detail'[income] >= 70000, "High",
 "unknown"
)

week_num2 = WEEKNUM('public cc_detail'[week_start_date])
Revenue = 'public cc_detail'[annual_fees] + 'public cc_detail'[total_trans_amt] + 'public cc_detail'[interest_earned]
Current_week_Reveneue = CALCULATE(
 SUM('public cc_detail'[Revenue]),
 FILTER(
 ALL('public cc_detail'),
 'public cc_detail'[week_num2] = MAX('public cc_detail'[week_num2])))
Previous_week_Reveneue = CALCULATE(
 SUM('public cc_detail'[Revenue]),
 FILTER(
 ALL('public cc_detail'),
 'public cc_detail'[week_num2] = MAX('public cc_detail'[week_num2])-1)

𝐈𝐧𝐬𝐢𝐠𝐡𝐭𝐬:
1)	Sum of revenue by card category : The blue card generated the highest revenue of almost 46 million.
2)	Sum of revenue by education type : The revenue generated from the graduated is highest which is of 22 million.
3)	Sum of revenue by job type : The highest revenue generated is from the businessman which is of 17 million.
4)	Sum of interest earn : The total interest earned Is of rupees 78,43,382.
5)	Sum of revenue earned is 55 Million.
6)	Sum of interest earned is 8 Million.

So, this was the short over view of the data , also the data is analysed with the Quarter section that is Q1,Q2,Q3,Q4.
													



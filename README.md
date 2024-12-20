# Bank-Loan-Report-SQL-Project
## Overview
This project provides a detailed analysis of loan applications, funded amounts, payments received, interest rates, and Debt-To-Income (DTI) ratios, segmented by various factors such as loan status (Good/Bad), month, state, loan term, home ownership, and loan purpose.
## Objective
- analyze and categorize bank loan data.
- segment the loan data based on factors like loan status
- insights into loan performance and borrower characteristics using SQL.
- List and analyse content based on release years, countries, and durations.
## Dataset
<a href="https://github.com/mamatha203/Financial-Loan-SQL-Project/blob/main/financial_loan.csv">Dataset</a>
## Schema

<b>1.Total Loan Applications?</b>

select 

count(id) as Total_Loan_Applications 

from financial_loan;

<b>2.Calculate Month to date (MTD) loan Applications?</b>

select 

count(id) as Total_MTD_Loan_Aplications

from financial_loan

where month(issue_date)=12;

<b>3.Find Previous moth to date loan applications?</b>

select 

count(id) AS Total_PMTD_Loan_Applications

FROM financial_loan

where month(issue_date) = 11;

<b>4.Find Total Funded Amount Received by Bank?</b>

Select 

sum(loan_amount) as Total_funded_Amount 

from financial_loan;

<b>5.Calculate Month to Date funded amont by Bank?

select 

sum(loan_amount) as Total_MTD_Loan_Amount 

from financial_loan 

where Month(issue_date)=12;

<b>6.Find Total PMTD funded Amount by Bank?</b>

select 

sum(loan_amount) as Total_PMTD_Funded_Amount 

from financial_loan 

where Month(issue_date)=11;

<b>7.Calculate Total amount recived by Bank?</b>

select 

sum(total_payment) as Total_Amount_Recieved 

from financial_loan;

<b>8.Calculate MTD amount received by Bank?</b>

select 

sum(total_payment) as Total_MTD_Amount_Recieved 

from financial_loan

where Month(issue_date)=12;

<b>9.Calculate Total PMTD amount received by Bank?</b>

select 

sum(total_payment) as Total_PMTD_Amount_Recieved 

from financial_loan

where Month(issue_date)=11;

<b>10.Calculate Total Average Intrest rate ?</b>

select 

avg(int_rate)*100 as Avg_Int_rate 

from financial_loan; 

<b>11.Find month to date Average Intrest rate?</b>

select 

avg(int_rate)*100 as MTD_Avg_Int_rate 

from financial_loan

where month(issue_date)=12;

<b>12.Calculate Average PMTD Intrest Rate?</b>

select 

avg(int_rate)*100 as PMTD_Avg_Int_rate 

from financial_loan
 
where month(issue_date)=11;

<b>13.Calculate Total Average DTI ?</b>

select 

avg(dti)*100 as Avg_dti 

from financial_loan;

<b>14.Find month to date average DTI?</b>

 select 
 
 avg(dti)*100 as MTD_Avg_dti 
 
 from financial_loan
 
 where month(issue_date)=12;

 <b>15. Calculate Average PMTD DTI?</b>
 
 select 
 
 avg(dti)*100 as PMTD_Avg_dti 
 
 from financial_loan
 
 where month(issue_date)=11;

<b>16.What Percent of Good Loan issued by Bank?</b>

select 

(count(case when loan_status = "Fully Paid" or loan_status = "Current" then id end)*100.0)/

count(id) as Good_loan_Percentage 

from financial_loan;

<b>17.How many Good Loan Applications are issued?</b>

select 

count(id) AS Good_Loan_Applications 

FROM financial_loan

where loan_status = "Fully Paid" OR loan_status = "Current";

<b>18.How much Good Loan amount Funded?</b>

select 

sum(loan_amount) AS Good_loan_Funded_Amount 

FROM financial_loan

where loan_status = "Fully Paid" OR loan_status = "Current";

<b>19.How much Total Good Loan Payments Received?</b>

select 

sum(total_payment) AS Good_loan_Amount_received 

FROM financial_loan

where loan_status = "Fully Paid" OR loan_status = "Current";

<b>20.What percent of Bad Loan issued by Bank?</b>

select 

(count(case when loan_status = "Charged Off" then id end)*100.0)/

count(id) as Bad_loan_percentage 

from financial_loan;

<b>21.How many Bad Loan Appliactions are issued?</b>

select

count(id) AS Bad_Loan_Applications 

FROM financial_loan

where loan_status = "Charged Off";

<b>22.How much Bad Loan Amount Funded?</b>

select 

sum(loan_amount) AS Bad_loan_Funded_Amount 

FROM financial_loan

where loan_status = "Charged Off";

<b>23.How much Total Bad Loan Payments Received?</b>

select 

sum(total_payment) AS Good_loan_Amount_received 

FROM financial_loan

where loan_status = "Charged Off";

<b>24.Calculate applications,funded amount,total payments for each month?</b>

select 

month(issue_date) as month_number ,

monthname(issue_date) as Month_name,

count(id) as Total_loan_Applications,

sum(loan_amount) as Total_Funded_Amount,

sum(total_payment) as Total_Amount_Recieved

from financial_loan

group by 1,2

order by 1 asc;

<b>25.Calculate applications,funded amount,total payments for each State?</b>

select

address_state as state,

count(id) as Total_loan_Applications,

sum(loan_amount) as Total_Funded_Amount,

sum(total_payment) as Total_Amount_Recieved

from financial_loan

group by address_state,

order by address_state;

<b>26.Calculate total applications ,funded amount,payments received by each Term?</b>

select 

term as Term,

count(id) as Total_loan_Applications,

sum(loan_amount) as Total_Funded_Amount,

sum(total_payment) as Total_Amount_Recieved

from financial_loan

group by term,

order by term;

<b>27.Calculate applications,funded amount,total payments for each Employ length?</b>

select 

emp_length as Empployee_length,

count(id) as Total_loan_Applications,

sum(loan_amount) as Total_Funded_Amount,

sum(total_payment) as Total_Amount_Recieved

from financial_loan

group by emp_length

order by emp_length;

<b>28.Calculate applications,funded amount,total payments for each Purpose?</b>

select 

purpose as loan_purpose,

count(id) as Total_loan_Applications,

sum(loan_amount) as Total_Funded_Amount,

sum(total_payment) as Total_Amount_Recieved

from financial_loan

group by 1

order by 1;

<b>29.Calculate applications,funded amount,total payments for each Home owenrship?</b>

select home_ownership as Home,

count(id) as Total_loan_Applications,

sum(loan_amount) as Total_Funded_Amount,

sum(total_payment) as Total_Amount_Recieved

from financial_loan

group by 1

order by 1;






























 

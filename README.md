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

select count(id) as Total_Loan_Applications 

from financial_loan;

2.MTD Loan Applications

select count(id) as Total_MTD_Loan_Aplications

from financial_loan

where month(issue_date)=12;

3.PMTD Loan Applications

select count(id) AS Total_PMTD_Loan_Applications

FROM financial_loan

where month(issue_date) = 11;

4.Total Funded Amount

Select sum(loan_amount) as Total_funded_Amount 

from financial_loan;

5.MTD Total Funded Amount

select sum(loan_amount) as Total_MTD_Loan_Amount 

from financial_loan 

where Month(issue_date)=12;

6.PMTD Total Funded Amount

select sum(loan_amount) as Total_PMTD_Funded_Amount 

from financial_loan 

where Month(issue_date)=11;

7.Total Amount Received

select sum(total_payment) as Total_Amount_Recieved 

from financial_loan;

8.MTD Total Amount Received

select sum(total_payment) as Total_MTD_Amount_Recieved 

from financial_loan

where Month(issue_date)=12;

9.PMTD Total Amount Received

select sum(total_payment) as Total_PMTD_Amount_Recieved 

from financial_loan

where Month(issue_date)=11;

10.Average Interest Rate

select avg(int_rate)*100 as Avg_Int_rate 

from financial_loan; 

11.MTD Average Interest Rate

select avg(int_rate)*100 as MTD_Avg_Int_rate 

from financial_loan

where month(issue_date)=12;

12.PMTD Average Interest Rate

select avg(int_rate)*100 as PMTD_Avg_Int_rate 

from financial_loan
 
where month(issue_date)=11;

13.Avg DTI

select avg(dti)*100 as Avg_dti 

from financial_loan;

14.MTD Avg DTI 

 select avg(dti)*100 as MTD_Avg_dti 
 
 from financial_loan
 
 where month(issue_date)=12;

 15.PMTD Avg DTI  
 
 select avg(dti)*100 as PMTD_Avg_dti 
 
 from financial_loan
 
 where month(issue_date)=11;

16.Good Loan Percentage

select (count(case when loan_status = "Fully Paid" or loan_status = "Current" then id end)*100.0)/

count(id) as Good_loan_Percentage 

from financial_loan;

17.How many Good Loan Applications are issued?

select count(id) AS Good_Loan_Applications 

FROM financial_loan

where loan_status = "Fully Paid" OR loan_status = "Current";

18.How much Good Loan amount Funded?

select sum(loan_amount) AS Good_loan_Funded_Amount 

FROM financial_loan

where loan_status = "Fully Paid" OR loan_status = "Current";

Good Loan Amount Recieved

select sum(total_payment) AS Good_loan_Amount_received 

FROM financial_loan

where loan_status = "Fully Paid" OR loan_status = "Current";






















 

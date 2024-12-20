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

1.Total Loan Applications

select count(id) as Total_Loan_Applications 
from financial_loan;

2.MTD Loan Applications

select count(id) as Total_MTD_Loan_Aplications from financial_loan
where month(issue_date)=12;

3.PMTD Loan Applications

select count(id) AS Total_PMTD_Loan_Applications FROM financial_loa
where month(issue_date) = 11;






 

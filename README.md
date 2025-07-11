# Banking Dashboard - Risk Analytics Project

## Overview
A Power BI dashboard for banking risk analysis that helps financial institutions make data-driven lending decisions and minimize loan default risk.

## Problem Statement
Banks need to assess loan repayment likelihood to minimize financial losses while lending to customers.

## Solution
Interactive dashboard providing insights on applicant profiles to support loan approval/rejection decisions based on risk assessment.

## Project Workflow
1. **MySQL Workbench** - Database setup and data import
2. **Google Colab** - Exploratory Data Analysis (EDA)
3. **Power BI** - Dashboard creation and visualization

## Dataset
Banking dataset with interconnected tables:
* Banking Relationship, Client-Banking, Gender, Investment Advisor, Period

## Key Features
* **Risk Assessment**: Loan repayment probability analysis
* **Customer Segmentation**: Income bands and demographic analysis
* **Financial Metrics**: Comprehensive KPIs for banking operations

## Key DAX Formulas

```dax
-- Total Clients
Total Clients = DISTINCTCOUNT('Clients - Banking'[Client ID])

-- Total Loan
Total Loan = [Bank Loan] + [Business Lending] + [Credit Cards Balance]

-- Bank Loan
Bank Loan = SUM('Clients - Banking'[Bank Loans])

-- Business Lending
Business Lending = SUM('Clients - Banking'[Business Lending])

-- Credit Cards Balance
Credit Cards Balance = SUM('Clients - Banking'[Credit Card Balance])

-- Total Deposit
Total Deposit = [Bank Deposit] + [Savings Account] + [Foreign Currency Account] + [Checking Accounts]

-- Bank Deposit
Bank Deposit = SUM('Clients - Banking'[Bank Deposits])

-- Savings Account
Savings Account = SUM('Clients - Banking'[Saving Accounts])

-- Checking Accounts
Checking Accounts = SUM('Clients - Banking'[Checking Accounts])

-- Foreign Currency Account
Foreign Currency Account = SUM('Clients - Banking'[Foreign Currency Account])

-- Total CC Amount
Total CC Amount = SUM('Clients - Banking'[Amount of Credit Cards])

-- Total Fees
Total Fees = SUMX('Clients - Banking', [Total Loan] * 'Clients - Banking'[Processing Fees])

-- Engagement Days
Engagment Days = DATEDIFF('Clients - Banking'[Joined Bank], TODAY(), DAY)

-- Engagement Length
Engagment Length = SUM('Clients - Banking'[Engagment Days])
```

## Dashboard Components
1. **Home** - Key metrics overview
2. **Loan Analysis** - Risk assessment and loan distribution
3. **Deposit Analysis** - Account trends and patterns
4. **Summary** - Executive insights

## Technologies Used
* MySQL Workbench
* Google Colab (Python)
* Power BI Desktop
* DAX (Data Analysis Expressions)

## Key Insights
* Private banks have higher client volumes
* Income-based risk segmentation
* Account type preferences by customer segments

## Installation
1. Set up MySQL database with banking.csv
2. Run EDA in Google Colab
3. Open Power BI file and refresh connections
4. Explore interactive dashboards

## Future Enhancements
* Real-time risk scoring
* Machine learning integration
* Automated reporting

---

*Demonstrates practical application of business intelligence in banking risk management.*

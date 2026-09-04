# Financial Performance

### Project Overview

This project involved analyzing a company's financial and sales performance using Power BI. The objective was to transform transactional financial data into an interactive management dashboard that provides insights into revenue, profitability, expenses, budget performance, customers, departments, and regional performance.

The project demonstrates my ability to perform data preparation, data modeling, DAX calculations, financial analysis, visualization, and business intelligence reporting.


### Tools Used

- Microsoft Excel – Data inspection and preparation
- Power BI – Data transformation, modeling, DAX and visualization
- Power Query – Data cleaning and transformation
- DAX – Financial KPIs and time-based calculations
- Power BI Model View – Data relationship and calendar modeling


### Business Problem

The company had transactional financial data but needed a clear way to monitor its financial performance and identify the major drivers of revenue and profitability.

The analysis was designed to answer questions such as:

- How much revenue did the company generate?
- How profitable was the business?
- How much was spent on COGS and operating expenses?
- Did actual revenue meet the budget?
- Which departments generated the most revenue?
- Which departments were the most profitable?
- Which customers generated the highest revenue?
- Which regions contributed most to revenue?
- How did revenue and profit change throughout the year?


### Dataset

The dataset contained 2,000 financial transactions covering a one-year period.

The main fields included:

| Field                | Description                             |
| -------------------- | --------------------------------------- |
| Transaction ID       | Unique transaction identifier           |
| Transaction Date     | Date of transaction                     |
| Customer             | Customer identifier                     |
| Region               | Sales region                            |
| Department           | Business/product department             |
| Sales Representative | Salesperson responsible for transaction |
| Quantity             | Units sold                              |
| Unit Price           | Price per unit                          |
| Gross Sales          | Sales before discount                   |
| Discount             | Discount given                          |
| Tax                  | Tax charged                             |
| Revenue              | Final revenue                           |
| COGS                 | Cost of goods sold                      |
| Operating Expense    | Operating costs                         |
| Marketing Cost       | Marketing expenditure                   |
| Net Profit           | Profit after relevant costs             |
| Budget               | Budget/target amount                    |



### Data Preparation

The dataset was first reviewed to understand the structure, fields, data types and financial variables.
Using Power Query, the data was prepared for analysis by ensuring that:

- Transaction dates were correctly recognized as dates.
- Numerical financial fields were stored as numerical values.
- Transaction IDs could be used to identify individual transactions.
- Revenue, expenses and profit fields were suitable for aggregation.
- The dataset was structured for use in Power BI.


### Calendar Table

A dedicated Calendar table was created in Power BI to support time-based analysis.
The Calendar table included fields such as:

- Date
- Year
- Month
- Month Number
- Quarter

The Calendar table was connected to the financial dataset using:

Calendar[Date] → Financial Dataset[Transaction_Date]

with a: **1 : * (One-to-Many) relationship**

This allowed the dashboard to perform monthly and time-based analysis and enabled measures such as YTD Revenue and Revenue Growth.


### DAX Measures

Several DAX measures were created to calculate the financial KPIs.

    Total Revenue =

    SUM('Financial Dataset'[Revenue])


    Total Profit =
    
    SUM('Financial Dataset'[Net_Profit])


    Total Gross Sales =
    
    SUM('Financial Dataset'[Gross_Sales])


    Total COGS =
    
    SUM('Financial Dataset'[Cost_of_Goods_Sold])


    Total Operating Expense =

    SUM('Financial Dataset'[Operating_Expense])


    Total Marketing Expense =

    SUM('Financial Dataset'[Marketing_Cost])


    Profit Margin % =

    DIVIDE([Total Profit], [Total Revenue], 0)


    Budget Variance =
    
    [Total Revenue] - SUM('Financial Dataset'[Budget])


    Average Revenue per Transaction =
   
    DIVIDE( [Total Revenue],
   
    DISTINCTCOUNT('Financial Dataset'[Transaction_ID]),0)



## Dashboard 1 — Financial Performance Overview

The first dashboard focuses on the company's overall financial health.


| KPI                         |      Result |
| --------------------------- | ----------: |
| **Total Revenue**           |    **534M** |
| **Total Profit**            | **129.19M** |
| **Total Gross Sales**       |    **536M** |
| **Total Operating Expense** |  **59.66M** |
| **Budget Variance**         | **-12.55M** |
| **Total COGS**              |    **283M** |
| **Total Transactions**      |      **2K** |

These figures provide management with a quick summary of the company's financial position.

*Profitability*

The company generated approximately **129.19M** in net profit from **534M** in revenue.

This represents an approximate profit margin of: **24.2%**


### Revenue Performance

The Revenue Trend by Month visual showed noticeable differences in monthly revenue.

The strongest month was: **July — approximately 53.7M**

The weakest month was: **October — approximately 38.1M**

Other notable months included:

- May — 48.0M
- December — 47.0M
- August — 46.8M
- April — 45.5M
- November — 45.2M
- March — 44.7M
- January — 43.3M
- June — 42.7M
- February — 40.2M
- September — 39.2M

**Key insight**

Revenue declined considerably from the high of **53.7M** in July to **38.1M** in October, suggesting a period of weaker sales performance toward the end of the year.


### Profit Performance

The Profit Trend by Month showed that July was also the strongest month for profitability.

Highest monthly profit: **July — 12.3M**

Lowest monthly profit: **October — 9.2M**

The profit trend generally followed the revenue trend, indicating that changes in sales were an important driver of overall profitability.



### Budget Performance

The dashboard recorded: Budget Variance of **-12.55M**

This means actual revenue was approximately **12.55M** below the budget/target based on the measure used.

This is an important management finding because although the company generated 534M in revenue, it did not fully achieve its overall budget target.

The budget-versus-revenue visual allows management to identify the months where actual performance was below or above the expected target.



## Dashboard 2 — Sales & Business Performance

The second dashboard focuses on understanding what is driving the company's financial performance.

It analyzes:

- Customers
- Departments
- Regions
- Profitability by department
- Revenue concentration


### Revenue by Department

The dashboard showed that Furniture was the highest revenue-generating department.

The remaining departments—Electronics, Home Appliances, Groceries and Clothing—recorded relatively similar revenue levels.

This suggests that while Furniture was the leading department, revenue was not heavily dependent on a single department.


**Business implication**

Management could investigate what is driving Furniture's stronger performance and determine whether the same strategies can be applied to the other departments.


### Profit by Department

The Total Profit by Department analysis showed that Furniture also performed strongly in profitability.

The departments were relatively close in profit compared with their revenue levels, suggesting that profitability was not dramatically concentrated in one business area.

This is useful because a department can generate high revenue but still have weak profitability if its costs are too high.



### Top Customers

The Top 10 Customers by Revenue visual identified the company's highest-value customers.

The leading customers included:

- Customer_170
- Customer_088
- Customer_038
- Customer_020
- Customer_153
- Customer_033
- Customer_054
- Customer_198
- Customer_049
- Customer_014

**Business implication**

These customers represent an important segment for customer retention strategies because losing a high-value customer could have a disproportionate effect on revenue.


### Regional Analysis

The dashboard also included Revenue by Region to evaluate geographic performance.

This allows management to compare the company's sales contribution across its different regions and identify areas that may require:

- Additional marketing
- Sales support
- Customer acquisition strategies
- Resource allocation

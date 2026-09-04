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

# Financial Performance & Business Analysis Dashboard


## Project Structure

- Project Overview
- Tools Used
- Business Problem
- Dataset
- Data Preparation
- Calendar Table
- DAX Measures
- Dashboard 1 — Financial Performance Overview
- Dashboard 2 — Sales & Business Performance
- Key Findings
- Recommendations

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


# Preview of Dataset

<img width="892" height="486" alt="Image" src="https://github.com/user-attachments/assets/e2c52f27-cdf2-4d37-8f8f-b725eda77dfd" />




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


# Preview of Calendar Table

<img width="757" height="376" alt="Image" src="https://github.com/user-attachments/assets/3c32ea46-f7a4-4c05-8b61-d6a23018eca9" />



# Preview of Data Modeling & Relationship Design

<img width="712" height="333" alt="Image" src="https://github.com/user-attachments/assets/28556e05-3d7c-4af1-bf4e-ac8113e4c8ff" />



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

*Profitability*: The company generated approximately **129.19M** in net profit from **534M** in revenue. This represents an approximate profit margin of: **24.2%**


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


# Preview of Financial Performance Dashboard


<img width="742" height="413" alt="Image" src="https://github.com/user-attachments/assets/41c51e7d-08b7-42c5-a152-e1d355a78259" />



## Dashboard 2 — Sales & Business Performance

### Purpose

This dashboard analyzes the company's sales drivers and business performance, focusing on customers, departments, profitability, and regional revenue.

**Overall Performance KPIs**

The dashboard provides a high-level summary of the company's performance:

| KPI                    |      Result |
| ---------------------- | ----------: |
| **Total Revenue**      |    **534M** |
| **Total Profit**       | **129.19M** |
| **Total COGS**         |    **283M** |
| **Total Transactions** |      **2K** |


**Interpretation**

The company generated **534M** in total revenue across approximately **2,000** transactions, generating **129.19M** in total profit.

The **283M** COGS represents the largest direct cost associated with generating the company's revenue.


### Revenue by Customer

The dashboard identifies the Top **10** customers by revenue.


| Rank | Customer         |  Revenue |
| ---: | ---------------- | -------: |
|    1 | **Customer_170** | **6.3M** |
|    2 | **Customer_088** | **5.9M** |
|    3 | **Customer_038** | **5.5M** |
|    4 | **Customer_020** | **5.4M** |
|    5 | **Customer_153** | **5.4M** |
|    6 | **Customer_033** | **5.2M** |
|    7 | **Customer_054** | **5.1M** |
|    8 | **Customer_198** | **4.7M** |
|    9 | **Customer_049** | **4.7M** |
|   10 | **Customer_014** | **4.6M** |


**Key insight**

**Customer_170** was the largest individual customer, contributing approximately **6.3M** in revenue.

The Top 10 customers each generated between 4.6M and 6.3M, highlighting a group of high-value customers that could be important for customer retention and relationship management.


### Revenue by Department

The dashboard shows the following departmental revenue:

| Department          |  Revenue |
| ------------------- | -------: |
| **Furniture**       | **115M** |
| **Electronics**     | **106M** |
| **Home Appliances** | **105M** |
| **Groceries**       | **104M** |
| **Clothing**        | **104M** |


**Key insight**

Furniture was the highest revenue-generating department at **115M**.

Electronics followed with **106M**, while Home Appliances generated **105M**.

Groceries and Clothing both generated approximately **104M**.

The relatively small gap between the departments indicates that revenue is fairly diversified across the business, although Furniture is currently the strongest contributor.


### Profit by Department

The dashboard also compares profitability across departments.

| Department          | Net Profit |
| ------------------- | ---------: |
| **Furniture**       |    **28M** |
| **Electronics**     |    **26M** |
| **Clothing**        |    **26M** |
| **Home Appliances** |    **25M** |
| **Groceries**       |    **25M** |


**Key insight**

Furniture generated the highest departmental profit at approximately **28M**.

Electronics and Clothing followed at approximately **26M** each, while Home Appliances and Groceries generated approximately **25M** each.

This is consistent with the revenue analysis: Furniture is both the highest-revenue and highest-profit department.


### Revenue by Region

The dashboard shows four regional markets:

| Region    |  Revenue |
| --------- | -------: |
| **North** | **142M** |
| **West**  | **135M** |
| **South** | **134M** |
| **East**  | **123M** |


**Key insight**

The North was the strongest-performing region, generating approximately **142M**.

The West followed with 135M, while the South generated **134M**.

The East recorded the lowest regional revenue at **123M**.

There is therefore a **19M** difference between the highest-performing region (North) and the lowest-performing region (East).


### Regional Performance Ranking

The regions can be ranked:

- North — 142M
- West — 135M
- South — 134M
- East — 123M

The North generated approximately **26.6%** of total company revenue based on the dashboard's **534M** total.

The East contributed approximately **23.0%**.

This suggests that although the North is the leading region, the company's revenue is still relatively distributed across the four regions.


### Quarter Analysis

The dashboard includes a Quarter slicer with:

- Q1
- Q2
- Q3
- Q4

This allows management to filter the entire dashboard and examine customer, department and regional performance by quarter.

For example, management can select Q1 and immediately see:

- Which customers generated the most revenue
- Which department performed best
- Which region generated the most revenue
- How profitable the business was during that quarter

This makes the dashboard interactive rather than simply presenting static figures.


# Preview of Sales and Business Performance Dashboard

<img width="737" height="415" alt="Image" src="https://github.com/user-attachments/assets/9b898f6e-d80e-44aa-87e5-9990d9fb6a0e" />



## Key Findings

Based on the completed dashboard, the major findings were:

- Strong overall profitability:  The company generated 534M in revenue and 129.19M in net profit, indicating a healthy overall profit position.

- Profit margin was approximately 24.2%: The company generated roughly 24.2% profit relative to revenue.

- July was the strongest month: July recorded the highest revenue at approximately 53.7M and the highest profit at approximately 12.3M.

- October was the weakest month:  October recorded the lowest revenue at approximately 38.1M and the lowest profit at approximately 9.2M.

- Budget performance requires attention: The company recorded a -12.55M budget variance, indicating that actual revenue fell below the budget target.

- Furniture was the strongest department: Furniture generated the highest revenue and was also among the strongest departments in profitability.

- Revenue was relatively diversified: Although Furniture led revenue, the other departments were relatively close, reducing dependence on a single department.

- High-value customers can be identified: The customer analysis highlighted the top 10 revenue-generating customers, providing an opportunity for targeted retention strategies.



## Recommendations

Based on the analysis, I would recommend that management:

-  Investigate the decline after July: Analyze why revenue fell from 53.7M in July to 38.1M in October.

- Improve budget planning: Investigate the factors contributing to the -12.55M budget variance and improve future forecasting.

- Strengthen weaker departments: Analyze why some departments generate lower revenue and determine whether pricing, marketing or product strategies need adjustment.

- Retain high-value customers: Develop targeted retention strategies for the top revenue-generating customers.

- Leverage Furniture's performance: Identify the factors behind Furniture's strong performance and replicate successful strategies across other departments.

- Monitor operating costs: With 59.66M in operating expenses and 283M in COGS, management should continuously monitor cost efficiency to protect margins.

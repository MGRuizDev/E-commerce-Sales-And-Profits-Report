### E-commerce-Sales-And-Profits-Report
The project is done mainly with Power BI, with ficticious data obtained on the Microsoft Power BI analyst certificate in Coursera.


#### Task
Analysis of sales performance. ( America's leading retailer of home improvement tools and items )
Design a report for sales and profits of a commercial business that buys and sells products. The most important key metrics and visuals and what possible insights we could get through their exploration.


#### Proposal

The need to create a system that will help this business to have a clear view of their sales analytics, and be able to take action decisions promptly and efficiently. With the business increasing its capacity and bigger market amplitude, in order to monitor a healthy trend of their profits, they required the instrumentations and insights into what is keeping, if that is the case, the positive trend and how to maintain it.


#### Extract

Information:  Sales, Purchase, and  Countries.
Source: Excel file (.xls)
Method: Manually by email from Sales manager.
Condition: Dirty. Duplicates, Empty values, Wrong data types, Syntax Errors.

Information: Historical Currency Exchange.
Source: Python Script (Read multiple lines string variable with csv format)
Method: Manual by Git Repository from Developer.
Condition: Clean.



#### Transform

Prepare the sales data worksheet to ensure accuracy. 

##### CLEANING. 

Working with copied data.
I have fixed syntax errors, data types errors and duplicates from the different tables.

##### TRANSFORMATION. 

New Tables Defined (using DAX code):

Calendar: for temporal data analysis and reporting.
Sales in USD: sales and profits metrics, to consolidate data on US Dollar.

New Columns Created: 

On the Sales Table.
Gross Revenue, Total Tax, and Net Revenue ( by subtracting tax from the gross amount ), to reflect the appropriate total amount of sales. 

On the Sales USD Table.
Monthly, Quarterly, and Yearly Profit margin. 


New Measures ( time-based summaries ):

Year To Date Profit.
Median Sales (to assess performance stability).



Database Model Design: 

I have constructed a snowflake schema tailored for the data model, by establishing and specifying the relationships between the tables in the data model.

A one-to-one relationship between the Countries and Exchange Data tables based on the Exchange ID field.
A many-to-one relationship between the Sales and Countries tables based on the Country ID field.
A one-to-one relationship between the Purchases and Sales tables based on the OrderID field.
A many-to-one relationship between the Calendar and Purchases table based on the Date field.
A many-to-one relationship between the Sales in USD and Sales tables based on the OrderID field.
All Relations with the cross-filter direction set to Both.




#### Visualization (analysis)

#### Findings

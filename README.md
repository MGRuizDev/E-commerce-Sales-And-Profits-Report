### E-commerce-Sales-And-Profits-Report
The project is done mainly with Power BI, with ficticious data obtained 
on the Microsoft Power BI analyst certificate in Coursera.

<br/>
<br/>
<br/>

#### Task
Analysis of sales performance (America's leading retailer of home improvement tools and items)
Design a report for sales and profits of a commercial business that buys and sells products. 
The most important key metrics and visuals and what possible insights we could get through their exploration.

<br/>
<br/>
<br/>

#### Proposal

The need to create a system that will help this business to have a clear view of their sales analytics, 
and be able to take action decisions promptly and efficiently. 
With the business increasing its capacity and bigger market amplitude, in order to monitor a healthy trend of their profits, 
they required the instrumentations and insights into what is keeping, if that is the case, the positive trend and how to maintain it.

<br/>
<br/>
<br/>

#### Extract

    * Information:  Sales, Purchase, and  Countries.
    * Source: Excel file (.xls)
    * Method: Manually by email from Sales manager.
    * Condition: Dirty.
    
    * Information: Historical Currency Exchange.
    * Source: Python Script (string variable with csv format)
    * Method: Manual by Git Repository from Developer.
    * Condition: Clean.

<br/>
<br/>
<br/>

#### Transform

Prepare the sales data worksheet to ensure accuracy. 

##### CLEANING. 

Working with copied data.
I have fixed syntax errors, data types errors, and duplicates from the different tables.

##### TRANSFORMATION. 

  ###### New Tables Defined (using DAX code):

        * Calendar: for temporal data analysis and reporting.
        * Sales in USD: sales and profits metrics, to consolidate data on US Dollar.
        * PurchaseMissingData: There was missing data from Purchase table. 
		It was needed to create a new table with the missed data to Append it to Purchase.

  ###### New Columns Created: 

        * On the Sales Table.
          Gross Revenue, Total Tax, and Net Revenue, 
	  (to reflect the appropriate total amount of sales). 
        
        * On the Sales USD Table.
          Monthly, Quarterly, and Yearly Profit margin. 


  ###### New Measures ( time-based summaries ):

        * Year To Date Profit.
        * Median Sales (to assess performance stability).




###### Database Model Design: 

I have constructed a snowflake schema tailored for the data model, by establishing and specifying the relationships between the tables in the data model.



![Model view of the dataset](/images/ModelView.png)



    * A one-to-one relationship between the Countries and Exchange Data tables based on the Exchange ID field.
    * A many-to-one relationship between the Sales and Countries tables based on the Country ID field.
    * A one-to-one relationship between the Purchases and Sales tables based on the OrderID field.
    * A many-to-one relationship between the Calendar and Purchases table based on the Date field.
    * A many-to-one relationship between the Sales in USD and Sales tables based on the OrderID field.
    * All Relations with the cross-filter direction set to Both.



<br/>
<br/>
<br/>
<br/>
<br/>
<br/>




#### Visualization (analysis)

##### Sales Overview


![Sales Overview page of report](/images/SalesOverview.png)


Pie Chart: Median Sales distribution by country
The median sale price measures the “middle” price of items that sold (half of the items sold for a higher price and half sold for less). 
Measure of central tendency for skewed distributions or distributions with outliers.

Line chart: Median sales over time
Forcast: Set Units to Days, Length to 2, Confidence interval to 99%.
We notice the trend suffer a decline over time.

Card Visual: Median Sales 


Map: Gross Revenue and Net Revenue USD by country.
The money the business earns by selling a product or service.
Gross revenue are earnings before deducting expenses.
Net revenue are earnings after subtracting expenses.

Table: Product categories - net revenue - best selling product - best selling customer
By showing the best selling product and customers you can allocate resources and efforts to the top performers.


Slicer: Countries
Filters page visuals, except Stock and Product Slicer.



<br/>
<br/>
<br/>
<br/>
<br/>
<br/>




##### Profits Overview



![Profits Overview page of report](/images/ProfitOverview.png)



Donut Chart: Yearly Profit Margin by Country
Low margin is 5%, a healthy margin is 10%, and a high margin is 20% but can vary across industries. 
Value in percentage that shows how much profit a company makes for each dollar of revenue after subtracting costs.

Area Chart: Yearly Profit Margin over Time
Profit margin metrics can help companies understand their financial health and make decisions to improve it.


Card visuals: YTD Profit  and  Quarterly Profit
The amount of profit or loss an investment has made since the beginning of the current year.

Line chart: Cost vs Revenue over time
Comparison of these to trends give us a perspective of how close they are getting to each other,
and the downward trend they are following.

Cluster Bar: Total taxes - Total cost - Net Revenue
Another perspective of these important values.


Slicer: Countries
Filters page visuals, except Stock and Product Slicer.


<br/>
<br/>
<br/>
<br/>
<br/>
<br/>



  
##### Customers Overview



![Customers Overview page of report](/images/CustomerOverview.png)



Clustered Bar Chart:  Loyalty Points by Country
Points programs allow customers to earn points when they spend, and the points can then be redeemed at a later date.
Showing the most loyal customers.

Column/Bar chart:  Net Sales By Customers and location
Showing the customer value and the country with most of the sales.

Scattered chart: Customer median Sales by Sales Rep.
Showing the Customer and Sales Representative relation, and sales effect.


Slicer: Countries
Filters page visuals, except Stock and Product Slicer.



<br/>
<br/>
<br/>
<br/>
<br/>
<br/>




##### Product Overview



![Product Overview page of report](/images/ProductOverview.png)



Column Chart: Quantity Sold by Product Category and Product Name having Drilldown function.
Showing what product is more popular.
What products have high demand, or have gain preference by customers.


Pie chart: Median Sales by Product Category
Showing the Top Performers Categories.


Column or Bar: Highest rank suppliers
Showing which suppliers are more reliable and possible represent a better business relation.


Card visuals: Stock 
Inventory levels. Can be used to compare the average inventory value to the average sales value.
Determine how quickly they're liquidating stock, and how much capital they have invested in inventory.


Slicer: Product Category
Sync only to the stock card visual. Showing individual stock by category.


Slicer: Countries
Filters page visuals, except Stock and Product Slicer.




#### Findings

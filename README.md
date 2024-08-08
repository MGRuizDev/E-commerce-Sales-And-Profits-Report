### E-commerce Sales And Profits Report
The project is done mainly with Power BI, and it is a ficticious company which data was obtained 
through the Microsoft Power BI analyst certificate in Coursera.

<br/>
<br/>
<br/>

#### Task
Analysis of sales performance for one of America's leading retailer of home improvement tools and items.
Design a report for sales and profits of this commercial business that buys and sells products. 
Share the most important key metrics and visuals and what possible insights we could get through their exploration.

<br/>
<br/>
<br/>

#### Proposal

The need to create a system that will help this business to have a clear view of their sales analytics, 
and be able to take action/decisions promptly and efficiently. 
With the business increasing its capacity and wider market amplitude, in order to monitor a healthy trend of their profits, 
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

The original files had been safely storage, so I will work with copied data.
I have fixed syntax errors, data types errors, and duplicates from the different tables.

##### TRANSFORMATION. 

  ###### New Tables Defined (using DAX code):

        * Calendar: for temporal data analysis and reporting.
        * Sales in USD: sales and profits metrics, to consolidate data on US Dollar.
        * PurchaseMissingData: There was missing data from Purchase table, which would cause false results. 
		It was needed to create a new table with the missed data that was recovered, then append it to the Purchase table.

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

I have constructed a snowflake schema tailored for the dataset, by establishing and specifying the relationships between the tables in the data model.



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


Pie Chart: Median Sales distribution by country. <br/>
The median sale price measures the “middle” price of items that sold (half of the items sold for a higher price and half sold for less). 
Measure of central tendency for skewed distributions or distributions with outliers.

Line chart: Median sales over time. <br/>
With a forcast; Set Units to Days, Length to 2, Confidence interval to 99%.
I noticed the trend suffered a decline over time.

Card Visual: Median Sales. 


Map: Gross Revenue and Net Revenue USD by country. <br/>
The money the business earns by selling a product or service.
Gross revenue are earnings before deducting expenses.
Net revenue are earnings after subtracting expenses.

Table: Product categories - net revenue - best selling product - best selling customer. <br/>
By showing the best selling product and customers you can allocate resources and efforts to the top performers.


Slicer: Countries. <br/>
Filters page visuals.



<br/>
<br/>
<br/>
<br/>
<br/>
<br/>




##### Profits Overview



![Profits Overview page of report](/images/ProfitOverview.png)



Donut Chart: Yearly Profit Margin by Country. <br/>
Low margin is 5%, a healthy margin is 10%, and a high margin is 20% but can vary across industries. 
Value in percentage that shows how much profit a company makes for each dollar of revenue after subtracting costs.

Area Chart: Yearly Profit Margin over Time. <br/>
Profit margin metrics can help companies understand their financial health and make decisions to improve it.


Card visuals: YTD Profit  and  Quarterly Profit. <br/>
The amount of profit or loss an investment has made since the beginning of the current year.

Line chart: Cost vs Revenue over time. <br/>
Comparison of these two trends give us a perspective of how close they are getting to each other,
and the downward trend they are following.

Cluster Bar: Total taxes - Total cost - Net Revenue. <br/>
Another perspective of the relation of these important values.


Slicer: Countries. <br/>
Filters page visuals.


<br/>
<br/>
<br/>
<br/>
<br/>
<br/>



  
##### Customers Overview



![Customers Overview page of report](/images/CustomerOverview.png)



Clustered Bar Chart:  Loyalty Points by Country. <br/>
Points programs allow customers to earn points when they spend, 
and the points can then be redeemed at a later date.
Showing the most loyal customers.

Column/Bar chart:  Net Sales By Customers and location. <br/>
Showing the customer value and the country with most of the sales.

Scattered chart: Customer median Sales by Sales Rep. <br/>
Showing the Customers with their Sales Representatives relation, and sales effectivity.


Slicer: Countries <br/>
Filters page visuals.



<br/>
<br/>
<br/>
<br/>
<br/>
<br/>




##### Product Overview



![Product Overview page of report](/images/ProductOverview.png)



Column Chart: Quantity Sold by Product Category and Product Name having Drilldown function. <br/>
Showing what product is more popular.
What products have high demand, or have gain preference by customers.


Pie chart: Median Sales by Product Category. <br/>
Showing the Top Performers Categories.


Column or Bar: Highest rank suppliers. <br/>
Showing which suppliers are more reliable and possible represent a better business relation.


Card visuals: Stock. <br/>
Inventory levels. Can be used to compare the average inventory value to the average sales value.
Determine how quickly they're liquidating stock, 
and how much capital they have invested in inventory.


Slicer: Product Category. <br/>
Sync only to the stock card visual. Showing individual stock by category.


Slicer: Countries. <br/>
Filters page visuals, except Stock and Product Slicer.



<br/>
<br/>
<br/>
<br/>
<br/>
<br/>



#### Optimization

The stakeholders will appreciate a report/dashboard that is fast, efficient and runs smoothly. 
Sometimes complex DAX queries (if working with Power BI) or visualization, useless data, 
and bad data model decisions, make long loading time and hard interaction with dynamic visuals. 
In order to avoid this, we need to optimize it.
Power BI has a tool to observe some parameters that I can, if need it, adjust to improve the performance; 
by running the Performance Analyzer tool, I can enhance report generation and ensure fast loading times. 

After using the tool the results came positive. This is an Efficient Report.


<br/>
<br/>
<br/>
<br/>
<br/>


#### Findings

United Arab Emirates leads on Revenue having a 63% of sales followed
by France, UK, Australia, and at the bottom is the USA.

<br/>
<br/>

In 5 months we have seen an overall sales downward trend
with a forecast dipping more to the bottom. Working with such small data (merely about a year), 
this might assume a normal trend that is looking at its bottom to go back up in the next months.

<br/>
<br/>

Australia, and the UK are going down, the United Arabs Emirates is strongly growing
followed by France and USA.

<br/>
<br/>

Very radical trend sales with most of them on July taking the trend up, then suffering a decline in August, 
following very strong spikes up at the end of August and at the beginning of September, 
going back down in the beginning of October 
(to observe these add "day" to date in x-axis on visualization format). 
This appears to be the normal yearly trend behavior, at least until I obtain more data.

<br/>
<br/>

Profits also show a great difference in revenue in July and October. 
Furniture, Gardening, and lighting are the biggest source of profit.

<br/>
<br/>

Security appears as the highest median sales by category
due to that it consists of only one expensive product, that is very popular. 
Probably the allocation of more resources in this category will be convenient.

<br/>
<br/>

Amelia Carter is one of the 10 top buyers and loyal customer, 
having Alice has her sales representative.






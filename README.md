### E-commerce-Sales-And-Profits-Report
The project is done mainly with Power BI, with ficticious data obtained on the Microsoft Power BI analyst certificate in Coursera.


#### Task
    Analysis of sales performance. ( America's leading retailer of home improvement tools and items )
    Design a report for sales and profits of a commercial business that buys and sells products. The most important key metrics and visuals and what possible insights we could get through their exploration.


#### Proposal

    The need to create a system that will help this business to have a clear view of their sales analytics, and be able to take action decisions promptly and efficiently. With the business increasing its capacity and bigger market amplitude, in order to monitor a healthy trend of their profits, they required the instrumentations and insights into what is keeping, if that is the case, the positive trend and how to maintain it.


#### Extract

    * Information:  Sales, Purchase, and  Countries.
    * Source: Excel file (.xls)
    * Method: Manually by email from Sales manager.
    * Condition: Dirty. Duplicates, Empty values, Wrong data types, Syntax Errors.
    
    * Information: Historical Currency Exchange.
    * Source: Python Script (Read multiple lines string variable with csv format)
    * Method: Manual by Git Repository from Developer.
    * Condition: Clean.



#### Transform

    Prepare the sales data worksheet to ensure accuracy. 

##### CLEANING. 

    Working with copied data.
    I have fixed syntax errors, data types errors, and duplicates from the different tables.

##### TRANSFORMATION. 

  ###### New Tables Defined (using DAX code):

        * Calendar: for temporal data analysis and reporting.
        * Sales in USD: sales and profits metrics, to consolidate data on US Dollar.
        * PurchaseMissingData: There was missing data from Purchase table. There was the need to create a new table with the missed data to Append it to Purchase

  ###### New Columns Created: 

        * On the Sales Table.
          Gross Revenue, Total Tax, and Net Revenue ( by subtracting tax from the gross amount ), to reflect the appropriate total amount of sales. 
        
        * On the Sales USD Table.
          Monthly, Quarterly, and Yearly Profit margin. 


  ###### New Measures ( time-based summaries ):

        * Year To Date Profit.
        * Median Sales (to assess performance stability).



###### Database Model Design: 

I have constructed a snowflake schema tailored for the data model, by establishing and specifying the relationships between the tables in the data model.

    * A one-to-one relationship between the Countries and Exchange Data tables based on the Exchange ID field.
    * A many-to-one relationship between the Sales and Countries tables based on the Country ID field.
    * A one-to-one relationship between the Purchases and Sales tables based on the OrderID field.
    * A many-to-one relationship between the Calendar and Purchases table based on the Date field.
    * A many-to-one relationship between the Sales in USD and Sales tables based on the OrderID field.
    * All Relations with the cross-filter direction set to Both.




#### Visualization (analysis)

##### Sales Overview
Pie Chart:
	Median Sales distribution by country
(The median sale price measures the “middle” price of items that sold, meaning that half of the items sold for a higher price and half sold for less. the most informative measure of central tendency for skewed distributions or distributions with outliers.)  Sales

Line chart:
Median sales over time
( with Forcast Set Units to Days.Set Forecast Length to 2.Set Confidence interval to 99%.) Sales


Card Visuals:
Median Sales 
(The median sale price measures the “middle” price of items that sold, meaning that half of the items sold for a higher price and half sold for less. the most informative measure of central tendency for skewed distributions or distributions with outliers)  Sales

Map:
gross and Net Revenue USD by country
	(the money a business earns by selling a product or service. your gross revenue is your earnings before you deduct your expenses, and your net revenue is your earnings after you subtract your expenses)  Sales, Profit

Table:
Product categories- net revenue- best selling product and customer


      KPI’s:
      Revenue  
      (the money a business earns by selling a product or service. your gross revenue is your earnings before you deduct your expenses, and your         net revenue is your earnings after you subtract your expenses)  Sales, Profit
      
      Gross Revenue USD
      	(the money a business earns by selling a product or service. your gross revenue is your earnings before you deduct your expenses, and your       net revenue is your earnings after you subtract your expenses)  Sales, Profit
       
      
      LineCharts:
      Seasonal demand fluctuations 
      	(demand in the industrial sector which rises and falls sharply in response to changing economic conditions and consumer spending patterns)        Sales, Customers


##### Profits Overview


Donut Chart:
	Yearly Profit Margin by Country
(Generally speaking, a good profit margin is 10 percent but can vary across industries. To determine gross profit margin, divide the gross profit by the total revenue for the year and then multiply by 100. To determine net profit margin, divide the net income by the total revenue for the year and then multiply by 100. a percentage that shows how much profit a company makes for each dollar of revenue after subtracting costs.) Profit

Area Chart:
	Yearly Profit Margin over Time
	(Profit margin can be calculated by dividing net income or gross profit by total revenue for the year and multiplying by 100. A good profit margin can vary by industry, but is generally considered to be between 5% and 10%. A low margin is 5%, a healthy margin is 10%, and a high margin is 20%. Profit margin metrics can help companies understand their financial health and make decisions to improve it.) 
Profit

Card visuals:
	YTD Profit
 	(the amount of profit or loss an investment has made since the beginning of the current year) Profit

line chart (sales and Profit Comparison):
	Sales vs Profit

Cluster Bar (sales and Profit Comparison):
	Sales vs Profit vs taxes

 



        KPI's: 
        Profit  
        ( the money your business keeps after accounting for all the expenses involved in generating that revenue. Net revenue only considers           expenses directly tied to revenue. In contrast, net profit further reduces revenue by deducting all other fixed and variable costs such as         payroll, rent, insurance, supplies, utilities, and maintenance)  Profit
        
        Operating Margin
        ( measures how much profit a company makes on a dollar of sales after paying for variable costs of production, such as wages and raw             materials, but before paying interest or tax. It is calculated by dividing a company's operating income by its net sales.) Profit
        
        Gross profit margin
        	 (calculated by subtracting direct expenses or cost of goods sold (COGS) from net sales (gross revenues minus returns, allowances and           discounts) ) Profit
        
        EBIT margin
        (EBIT margin, also known as operating margin, is a financial ratio that measures a company's profitability before interest and taxes as a         percentage of its total revenue. It's calculated by dividing earnings before interest and taxes (EBIT) by sales or net earnings. The                 formula for EBIT margin is:
        Quarterly EBIT Margin: (operating earnings) / (quarterly sales)
        TTM EBIT Margin: (last four quarters of operating earnings) / (last four quarters of sales)
          An EBIT Margin is the operating earnings over operating sales. This margin allows investors to understand true business costs of running       a       company, because parts of a company's property, plant, and equipment will eventually need to be replaced as they get used, broken             down,         decayed, etc.)  Profit
        
        Net profit margin
        	(Net profit margin (also called the return on sales ratio) is a widely used profitability indicator that gauges your company's financial       health. It is the percentage of sales revenue you have left after deducting operating expenses, depreciation, amortization, interest, and           income taxes)   Profit
        
        Return on Equity
        	(Return on equity (ROE) is the measure of a company's net income divided by its shareholders' equity. ROE is a gauge of a corporation's         profitability and how efficiently it generates those profits. The higher the ROE, the better a company is at converting its equity                   financing into profits.It's calculated by dividing a company's net income by its shareholders' equity, and is expressed as a                     percentage:%. Stakeholders' equity, also known as shareholders' equity, is a key metric for evaluating a company's financial health and           stability. It's calculated by subtracting a company's total liabilities from its total assets, including both current and non-current               assets)  Profit



  
##### Customers Overview


Clustered Bar Chart:
	Loyalty Points by Country.
(Points programs allow customers to earn points when they spend, and the points can then be redeemed at a later date. Tier programs allow customers different benefits depending on their rank, which they can earn after reaching spending limits)  Customers

Column/Bar chart:
Net Sales By Customers Name and location
(Where are sales, or better customers) Customers, Sales

Scattered chart
Customer median Sales by Sales Rep.


insights:
      KPI's:
      
      Customer lifetime value (CLV) 
      (a metric that estimates the net profit a company can expect to earn from a customer relationship over its entire lifespan) Customers
      
      LineCharts:
      Changes in customer preferences
      	(Customer preferences can change frequently and are influenced by many factors, including society, technology, and lifestyle. These changes can impact demand, causing it to increase or decrease. For example, if consumers prefer healthier food, demand for organic food may increase.)  Customers




##### Product Overview

Column Chart:
Quantity Sold by Product
(What product is more popular) Product, Sales

Pie chart:
Quantity Purchased
(What product has more demand)   Product, Sales

Card visuals:
Stock 
(inventory levels or inventory to sales ratio, also known as stock to sales ratio, compares the average inventory value to the average sales value and is one measure of a company's inventory level health. This KPI helps retailers determine how quickly they're liquidating stock, and how much capital they have invested in inventory.
Stock to sales ratio = Average stock value / Net sales value.
Average stock value = (Beginning inventory + Ending inventory) / 2.
Net sales = Gross sales – Sales returns, allowance and dicounts)  Product, Sales



Column or Bar (Product Performance):
Highest rank suppliers
(What products have temporal high demand, or have gain long time preference by customers) Product, Sales

    2 slicers each controlling and individual visual
    Integrate drilldown function to product category.




#### Findings

Data Dictionary for Gold Layer

Overview

The Gold Layer is the business level data representation, structured to support analytical and reporting use cases.  It consists of
dimension tables and fact tables for specific business metrics.

1. gold.dim_customers

Purpose - stores customers details enriched with demographic and geographic data

Columns
 
Column Name      |   Data type     |   Description                                                            |
-----------------|-----------------|--------------------------------------------------------------------------|
customer_key     | INT             | Surrogate key identifying each customer record in the dimmension table
customer_id      | INT             | Unique numerical identifier assigned to each customer
customer_number  |nvarchar(50)     | Alphanumeric identfier representing the customer
first_name       |nvarchar(50)     | The customers first name as recorded in the system
last_name        |nvarchar(50)     | The customers last name
country          |nvarchar(50)     | The country of residence for the cus   tomer
marital_status   |nvarchar(50)     | The marital status of customers
gender           |nvarchar(50)     | The customer's gender
birth_date       |date             | The date of birth of the customers YYYY-MM-DD
create_date      |date             | The date and tme the customer record was created in the system

2. gold.dim_products

Purpose - provides information about the products and their attributes

Columns

Column Name      |   Data type     |   Description                                                                        |
-----------------|-----------------|--------------------------------------------------------------------------------------|
product_key      |INT              | Surrogate key uniquely identifying each product record in the product dimension table
product_id       |INT              | A unique idenifier assigned to the product for internal tracking and refference
gender           |nvarchar(50)     | A structured alphanumeric code representing the product 
product_name     |nvarchar(50)     | Descriptive name of the product including details of type, color, and size
category_id      |nvarchar(50)     | A unique identifier for the product category linking to its high level classification
category         |nvarchar(50)     | The broader classification of the product to the group related product
subcategory      |nvarchar(50)     | A more detailed classification of th product within the category
maintenance      |nvarchar(50)     | Indicates whether the product requires maitenance  'Yes' or 'No'
cost             |INT              | The cost or base price of the unit
product_line     |nvarchar(50)     | The specific product line or series to which the product belongs 
start_date       |date             | The date that the product became available for sale or use

3. gold.fact_sales

Purpose - stores transactional sales data for analytical purposes

Columns

Column Name      |   Data type     |   Description                                                                        |
-----------------|-----------------|--------------------------------------------------------------------------------------|
order_number     |nvarchar(50)     | A unique alphanumeric identifer for each sales order
product_key      |INT              | A surrogate key linking order to product dimension table
customer_key     |INT              | A surrogate key linking order to customer dimension table
order_date       Idate             | The date when the order was placed
ship_date        |date             | The date that the order was shipped
due_date         |date             | The date when the order payment was due
sales_amount     |INT              | The total sales value for each order
quantity         |INT              | The number of units ordered for the product for that line item
price            |INT              | The price per unit for the line item
 

#Data Dictionary for Gold Layer

##Overview
###The Gold Layer is the business level data representation, structured to support analytical and reporting use cases.  It consists of
dimension tables and fact tables for specific business metrics.

###gold.dim_customers
 Purpose - stores customers details enriched with demographic and geographic data
 Columns
 Column Name      Data type        Description
customer_key      INT              Surrogate key identifying each customer record in the dimmension table
customer_id       INT              Unique numerical identifier assigned to each customer
customer_number  nvarchar(50)      Alphanumeric identfier representing the customer
first_name       nvarchar(50)      The customers first name as recorded in the system
last_name        nvarchar(50)      The customers last name
country          nvarchar(50)       The country of residence for the customer

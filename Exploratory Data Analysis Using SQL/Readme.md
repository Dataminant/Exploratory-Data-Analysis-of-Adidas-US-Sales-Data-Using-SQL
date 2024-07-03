# Exploratory Data Analysis of Adidas US Sales Dataset Using SQL

## Processes:
Given that the dataset was in Microsoft Excel CSV format, I had to import the CSV file into SQL Server Management Studio (SSMS) in order to perform data cleaning and manipulation to ensure I have an accurate and consistent data, also to improve the quality and reliability of the data for analysis.

## Creating table
```sql
CREATE TABLE Sales (
        retailer  CHARACTER VARYING (255),
	retailer_id INTEGER,
	invoice_date  DATE,
	region CHARACTER VARYING (255),
	state   CHARACTER VARYING (255),
	city  CHARACTER VARYING (255),
	product CHARACTER VARYING (255),
	price_per_unit INTEGER,
	units_sold  NUMERIC,
	total_sales NUMERIC,
	operating_profit NUMERIC,
	operating_margin NUMERIC,
	sales_method CHARACTER VARYING (255)
   
);
```

![Creating table](https://github.com/Dataminant/Exploratory-Data-Analysis-of-Adidas_US_Sales_Dataset_Using_SQL/blob/220e807be88d8cc7d379e06c84c243a3d951e76c/Exploratory%20Data%20Analysis%20Using%20SQL/Questions/Creating%20Table.jpg)

## Bulk insert values into table
```sql
--  Bulk insert values into table

BULK INSERT dbo.Sales
FROM 'C:\Users\HP\Desktop\Kaggle_Adidas_US_Sales.csv'
WITH
(

    FORMAT = 'CSV',
	FIRSTROW = 2

)
;

```

![Insert Values into Table](https://github.com/Dataminant/Exploratory-Data-Analysis-of-Adidas_US_Sales_Dataset_Using_SQL/blob/6901c8bcadc885646acd4363e22af5dc630a5cd7/Exploratory%20Data%20Analysis%20Using%20SQL/Questions/Bulk%20inserting%20details%20into%20Tabble.jpg)

## Preview of data in the table 
![Preview of data in the table](https://github.com/Dataminant/Exploratory-Data-Analysis-of-Adidas_US_Sales_Dataset_Using_SQL/blob/a9fb868305516f58d356644110371db8209d3b63/Exploratory%20Data%20Analysis%20Using%20SQL/Questions/Preview%20of%20dataset.jpg)

## Changing the table name 
![Changing the table name](https://github.com/Dataminant/Exploratory-Data-Analysis-of-Adidas_US_Sales_Dataset_Using_SQL/blob/5e355d19e691bc4b7a48ef9e82671b34504a6e09/Exploratory%20Data%20Analysis%20Using%20SQL/Questions/Changing%20the%20table%20name%20.jpg)

## Checking for null in dataset
```sql
-- Checking for NULL in the dataset
SELECT 
    SUM(CASE WHEN retailer IS NULL THEN 1 ELSE 0 END) AS retailer_null_count,
    SUM(CASE WHEN retailer_id IS NULL THEN 1 ELSE 0 END) AS retailer_id_null_count,
    SUM(CASE WHEN invoice_date IS NULL THEN 1 ELSE 0 END) AS invoice_date_null_count,
    SUM(CASE WHEN region IS NULL THEN 1 ELSE 0 END) AS region_null_count,
    SUM(CASE WHEN state IS NULL THEN 1 ELSE 0 END) AS state_null_count,
    SUM(CASE WHEN city IS NULL THEN 1 ELSE 0 END) AS city_null_count,
    SUM(CASE WHEN product IS NULL THEN 1 ELSE 0 END) AS product_null_count,
    SUM(CASE WHEN price_per_unit IS NULL THEN 1 ELSE 0 END) AS price_per_unit_null_count,
    SUM(CASE WHEN units_sold IS NULL THEN 1 ELSE 0 END) AS units_sold_null_count,
    SUM(CASE WHEN total_sales IS NULL THEN 1 ELSE 0 END) AS total_sales_null_count,
    SUM(CASE WHEN operating_profit IS NULL THEN 1 ELSE 0 END) AS operating_profit_null_count,
    SUM(CASE WHEN operating_margin IS NULL THEN 1 ELSE 0 END) AS operating_margin_null_count,
    SUM(CASE WHEN sales_method IS NULL THEN 1 ELSE 0 END) AS sales_method_null_count

FROM dbo.TheDataminant_Sales
```
![Checking for null in dataset](https://github.com/Dataminant/Exploratory-Data-Analysis-of-Adidas_US_Sales_Dataset_Using_SQL/blob/5e355d19e691bc4b7a48ef9e82671b34504a6e09/Exploratory%20Data%20Analysis%20Using%20SQL/Questions/Checking%20for%20null%20in%20dataset.jpg)


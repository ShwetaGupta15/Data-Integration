## Problem Description

In this problem, I am working on Adventureworks dataset (relational) who sells bikes and related products (parts & accessories). The dataset uses two channels to sell -
1. Direct to customers via internet
2. Indirectly through resellers (or stores)
The problem states to design the dimensional model considering the above dataset plus to find th rejects using the customer demographics, store demographics and order detail and order header csv files. These file are manually created which might have the unfiltered data (null) - will be rejects for given model.  
 
Business transactions tracked via - sales, purchases & inventory. These transaction may have the following dimension as below -
- Product Sold or purchased : Product Hierarchy - Products, SubCategories & Categories
- Address for customer, employees, stores & others Geography Hierarchy - City, State, Country
- Customers (Individuals buying over the internet)
- Ship, Order, Due, Purchase & other Dates Date Hierarchy Year, Quarter, Month, Day
- Employees including salespeople
- Vendors product and part suppliers
- Sales promotions

The facts include, which are as below  -
- fct_internetsales
- fct_storesales
- fct_internetsales_REJECTS  
- fct_storesales_REJECTS 

![image](https://user-images.githubusercontent.com/71230572/114281319-81939400-99f2-11eb-8dd7-726f7c4c205a.png)
![image](https://user-images.githubusercontent.com/71230572/114281340-b6075000-99f2-11eb-8c17-0a91652646ee.png)

### Database -
#### Sources Database used - AdventureWorks2019
Source Files - 
1. SourceCustomerDemographics.csv [CustomerDemographics.csv](https://github.com/ShwetaGupta15/Data-Integration/files/6290579/CustomerDemographics.csv)
2. StoreWithDemographics.csv [SalesOrderDetail_Revised.csv](https://github.com/ShwetaGupta15/Data-Integration/files/6290581/SalesOrderDetail_Revised.csv)
3. SalesOrderHeader_Revised.csv [SalesOrderHeader_Revised.csv](https://github.com/ShwetaGupta15/Data-Integration/files/6290577/SalesOrderHeader_Revised.csv)
4. SalesOrderDetail_Revised.csv [SalesOrderDetail_Revised.csv](https://github.com/ShwetaGupta15/Data-Integration/files/6290575/SalesOrderDetail_Revised.csv)

#### Target Database used - AdventureWorksDW (SQL Server & MySQL)
Target SQL Script [AdventureWorksDW_SQL_Scripts.zip](https://github.com/ShwetaGupta15/Data-Integration/files/6290821/AdventureWorksDW_SQL_Scripts.zip)

- The Facts of target database are developed from the existing tables (OrderDetail and OrderHeader) in the dataset which have no rejects as the data is crisp and clear whereas    the other two facts used the given csv files to find out the rejects and to understand the concept of rejects (or impure data). Using the rejects from the fact table I developed the table as 'DIM_Rejcts' which has the reject code and its related reason/description.


### Visualization
Visualization done based on the following requirements - 
1. Product Contribution of Sales
2. Comparison of Yearly Sales
3. Sales Promotions & Discounts
4. Product Sales by Geography (city, state, country)
5. Product Profits by Sales Territory
6. Top 5 Sales People Ranked
7. Top 10 Resellers (Stores) Ranked
8. Geography based Contribution to Sales
9. Two people related attributes correlated to their sales
10. Any reseller attributes (at least one) correlated to their sales

### Results
- Used Alteryx to load the SQL Server.
- Used Talend to load the MySQL.


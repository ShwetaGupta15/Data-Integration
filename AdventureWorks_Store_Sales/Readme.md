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

####                                             Fact Store Sales -
![image](https://user-images.githubusercontent.com/71230572/114281319-81939400-99f2-11eb-8dd7-726f7c4c205a.png)

####                                             Fact Internet Sales - 
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
- Some of the visualization snips are -
- ![image](https://user-images.githubusercontent.com/71230572/114287104-20cb8200-9a19-11eb-9110-69a1c2b9151e.png)
- ![image](https://user-images.githubusercontent.com/71230572/114292581-4b7f0000-9a44-11eb-8dbf-faca2aa0f618.png)

### Results
- Source to Target mappings, to identify the tables and columns used to load dimensions and facts in tha target databases [SourceToTargetMapping_SQLServer.xlsx](https://github.com/ShwetaGupta15/Data-Integration/files/6290834/SourceToTargetMapping_SQLServer.xlsx)

- Used Alteryx to load the SQL Server.
- ![image](https://user-images.githubusercontent.com/71230572/114292218-c0046f80-9a41-11eb-9b5c-f8ddc2f8edba.png)
- ![image](https://user-images.githubusercontent.com/71230572/114289133-562c9b80-9a2a-11eb-9115-924f541ca8f9.png)
- [Facts_Revised.pdf](https://github.com/ShwetaGupta15/Data-Integration/files/6291164/Facts_Revised.pdf)
- Using Fact base load I am separating the internet and reseller custumers based on the ONLINE_FLAG.
1. If ONLINE_FLAG = 1 then the customers belong to internet sales
2. If ONLINE_FLAG = 0 then the customers belong to reseller sales
- The inner join of tables loads the FACT tables whereas the left join of each table load the REJECT.
- If the table passes 0 or null in the left join means each row of the table joined where if the left join have some records means there are some records which does not satisfies the joining condition and these are the REJECTS.
- That ID will be given some value say "-99" which is the reject code and the reason would "ID doesen't exist"




- Used Talend to load the MySQL.
1. Fact_Internet and Fact_Reseller using the Revised CSV file.
-  ![image](https://user-images.githubusercontent.com/71230572/115138083-c7e28780-9fde-11eb-918f-d1fd07772391.png)
-  ![image](https://user-images.githubusercontent.com/71230572/115138333-4f7cc600-9fe0-11eb-9f9c-be8a65f05860.png)
-  Here, revised version of OrderHeader and OrderDetails CSV has been created which has reject values. Dimensions are inner joined to load the SK in Facts. I have added tChronometer to record the execution time of the job and the 'tAssert' tool to check if the expected number of columns loaded into the target database and logs error if not.
-  For rejects, catch lookup inner join reject is set to 'TRUE'. 
-  ![image](https://user-images.githubusercontent.com/71230572/115138536-b058ce00-9fe1-11eb-9ca9-b6e4ac150002.png)
-  Using truncate load for all the facts and dimensions for both Alteryx and Talend





## Problem Statement
This problem is the extended version of AdevntureWorks_Store_Sales where data includes new additions like -
1. Purchasing
2. Employees
3. Product

- When the bikes, bike components sold on AdventureWorks via internet or store, AdventureWorks purchases products from Vendors that they either resell or use as component in their own finished goods that they build and sell.
- The deliverables are designed to represent the Purchasing Data Warehouse, populate the tables using Talend & Alteryx into the databases MySQL & SQL Server and then to create visualizations using Tableau, PowerBI.

- All product purchase made by Adventureworks will be from Vendors, i.e. purchase orders
- List of products that might be purchased from Vendors, in other words, all the products that are not made by AdventureWorks
- Vendors that AdventureWorks might purchase products from
- Products that AdventureWorks might purchase from vendors and associated with the vendors that sell them.
- Vendors’ employees (contacts) who interact with AdventureWorks.
- Employees who have bought products from vendors and include attributes about those people such as address, email, phone, department they currently work in.
- Ship Methods
- Geography dimensions (Outrigger) that includes cities, state, countries.
- Data dimension.

### Schemas used to load Tables:

1. For Purchasing  (Vendors from whom products are purchased)-
![image](https://user-images.githubusercontent.com/71230572/117406621-2904c900-aec2-11eb-8537-90dd2706ce45.png)

2. Human Resources (Employess of AdventureWorks)- 
![image](https://user-images.githubusercontent.com/71230572/117406675-3b7f0280-aec2-11eb-849f-08d0008b3a19.png)

3. Manufacturing -


![image](https://user-images.githubusercontent.com/71230572/117407215-16d75a80-aec3-11eb-8afe-dc91a4c8adfd.png)

#### List of Dimensions & Facts:
![image](https://user-images.githubusercontent.com/71230572/117405590-bba46880-aec0-11eb-8119-89571555843f.png)

### Source Database Files:
- [EmployeeData.csv](https://github.com/ShwetaGupta15/Data-Integration/files/6444940/EmployeeData.csv)
- [IndividualCustomer.csv](https://github.com/ShwetaGupta15/Data-Integration/files/6444941/IndividualCustomer.csv)
- [PersonDemographics.csv](https://github.com/ShwetaGupta15/Data-Integration/files/6444942/PersonDemographics.csv)
- [SalesPerson.csv](https://github.com/ShwetaGupta15/Data-Integration/files/6444943/SalesPerson.csv)
- [StoreAddresses.csv](https://github.com/ShwetaGupta15/Data-Integration/files/6444944/StoreAddresses.csv)
- [StoreContacts.csv](https://github.com/ShwetaGupta15/Data-Integration/files/6444945/StoreContacts.csv)
- [StoreDemographics.csv](https://github.com/ShwetaGupta15/Data-Integration/files/6444946/StoreDemographics.csv)
- [VendorAddresses.csv](https://github.com/ShwetaGupta15/Data-Integration/files/6444947/VendorAddresses.csv)
- [VendorContacts.csv](https://github.com/ShwetaGupta15/Data-Integration/files/6444948/VendorContacts.csv)
- [EmployeePayHistoryAltered_202103291656.csv](https://github.com/ShwetaGupta15/Data-Integration/files/6527656/EmployeePayHistoryAltered_202103291656.csv)
- [EmployeePayRateChanges_202103281658.csv](https://github.com/ShwetaGupta15/Data-Integration/files/6527657/EmployeePayRateChanges_202103281658.csv)
- [ProductCostAltered_202103291657.csv](https://github.com/ShwetaGupta15/Data-Integration/files/6527658/ProductCostAltered_202103291657.csv)
- [PurchaseOrderDetailAltered_202103291632.csv](https://github.com/ShwetaGupta15/Data-Integration/files/6527659/PurchaseOrderDetailAltered_202103291632.csv)
- [PurchaseOrderHeaderAltered_202103291633.csv](https://github.com/ShwetaGupta15/Data-Integration/files/6527660/PurchaseOrderHeaderAltered_202103291633.csv)



### Target Database -
#### Srcipts for SQL Server & MySQL - [adventureWorksDW_SQL_Scripts.zip](https://github.com/ShwetaGupta15/Data-Integration/files/6439574/adventureWorksDW_SQL_Scripts.zip)

The tables in the dimesnions and facts are loaded using the the csv files. There are some dimensions which has the direct load whereas some have the dependencies on others, which fulfilled using joining conditions at the ETL end. Also, I have created SCD-2 for the dimensions - 
- dim_payhistory
- dim_productcosthistory
- dim_productpricehistory
in both Talend & Alteryx on modified_date.
Some of the jobs snapshots for Alteryx and Talend as follows -

Dim_Employee - [DimEmployee.pdf](https://github.com/ShwetaGupta15/Data-Integration/files/6445004/DimEmployee.pdf)

![image](https://user-images.githubusercontent.com/71230572/117522737-e4346d00-af69-11eb-9536-2bab7290e445.png)

- DimPayHishory (SCD Type 2) where I have used Multi-Row Formula component in Alteryx to create scd_end date column using where it checks for the value for each Row+1 and Formula component to create Active_Flag and to check if the scd_end is null then set the value for flag as "1" which shows this as the lastest record and the Running Total component which increments the value of version by 1 till it gets the scd_end as null. Hence, the SCD - 2 has been applied on the the column SCD_END.
- For other SCDs (dim_productcosthistory, dim_productpricehistory) the same has been applied.
 
![image](https://user-images.githubusercontent.com/71230572/117551235-a717bb80-aff9-11eb-814b-d03fd73f78c0.png)
![image](https://user-images.githubusercontent.com/71230572/119251075-4c35a680-bb59-11eb-8ed3-8113a8be3d0a.png)

- Fct_Purchase - The fact has been loaded using multiple dimension's SK using the inner join and the for each inner join which SK is not null, are loaded to FCT_Purchase_REJECT using the left join.
- [Fact_Purchase.pdf](https://github.com/ShwetaGupta15/Data-Integration/files/6446484/Fact_Purchase.pdf)

![image](https://user-images.githubusercontent.com/71230572/117552048-17284080-affe-11eb-8ab2-7f644920404e.png)

- Fct_WorkOrder and Fct_WorkOrder_Rejects in Talend. The Fact has been populated using the inner join where as for rejects '_Catch lookup inner join reject_' is set to **TRUE** and the similar procedure has been applied to other facts in talend.
- ![image](https://user-images.githubusercontent.com/71230572/119246452-8c376200-bb36-11eb-8eec-6d328148b2e8.png)
- ![image](https://user-images.githubusercontent.com/71230572/119246406-35318d00-bb36-11eb-941d-d0b7faf17880.png)
- SCD Type 2 in Talend (Dim_ProductCostHistory) usind the SCD Component- The SCD has been applied on the Product_SK as shown below in the SCD editor and the results captured in SQL Server. 
- ![image](https://user-images.githubusercontent.com/71230572/119249878-1a204680-bb51-11eb-85da-75f7aee06eca.png)
- ![image](https://user-images.githubusercontent.com/71230572/119249885-2a382600-bb51-11eb-8642-2ad0f844b59d.png)
- ![image](https://user-images.githubusercontent.com/71230572/119249896-3fad5000-bb51-11eb-994e-5e451914097c.png)






















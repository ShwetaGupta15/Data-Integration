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
- [DimEmployeePayHistory_Input.csv](https://github.com/ShwetaGupta15/Data-Integration/files/6444937/DimEmployeePayHistory_Input.csv)
- [DimProductCost_Input.csv](https://github.com/ShwetaGupta15/Data-Integration/files/6444939/DimProductCost_Input.csv)
- [EmployeeData.csv](https://github.com/ShwetaGupta15/Data-Integration/files/6444940/EmployeeData.csv)
- [IndividualCustomer.csv](https://github.com/ShwetaGupta15/Data-Integration/files/6444941/IndividualCustomer.csv)
- [PersonDemographics.csv](https://github.com/ShwetaGupta15/Data-Integration/files/6444942/PersonDemographics.csv)
- [SalesPerson.csv](https://github.com/ShwetaGupta15/Data-Integration/files/6444943/SalesPerson.csv)
- [StoreAddresses.csv](https://github.com/ShwetaGupta15/Data-Integration/files/6444944/StoreAddresses.csv)
- [StoreContacts.csv](https://github.com/ShwetaGupta15/Data-Integration/files/6444945/StoreContacts.csv)
- [StoreDemographics.csv](https://github.com/ShwetaGupta15/Data-Integration/files/6444946/StoreDemographics.csv)
- [VendorAddresses.csv](https://github.com/ShwetaGupta15/Data-Integration/files/6444947/VendorAddresses.csv)
- [VendorContacts.csv](https://github.com/ShwetaGupta15/Data-Integration/files/6444948/VendorContacts.csv)


### Target Database -
#### Srcipts for SQL Server & MySQL - [adventureWorksDW_SQL_Scripts.zip](https://github.com/ShwetaGupta15/Data-Integration/files/6439574/adventureWorksDW_SQL_Scripts.zip)

The tables in the dimesnions and facts are loaded using the the csv files. There are some dimensions which has the direct load whereas some have the dependencies on others, which fulfilled using joining conditions at the ETL end. Also, I have created SCD-2 for the dimensions - 
- dim_payhistory
- dim_productcosthistory
- dim_productpricehistory
in both Talend & Alteryx on modified_date.
Some of the jobs snapshots for Alteryx as follows -

Dim_Employee - [DimEmployee.pdf](https://github.com/ShwetaGupta15/Data-Integration/files/6445004/DimEmployee.pdf)

![image](https://user-images.githubusercontent.com/71230572/117522737-e4346d00-af69-11eb-9536-2bab7290e445.png)
- DimPayHishory (SCD Type 2)
![image](https://user-images.githubusercontent.com/71230572/117551235-a717bb80-aff9-11eb-814b-d03fd73f78c0.png)

















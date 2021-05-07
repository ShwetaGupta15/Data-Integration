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
- [DimEmployeePayHistory_Input.csv](https://github.com/ShwetaGupta15/Data-Integration/files/6439488/DimEmployeePayHistory_Input.csv)
- [DimProductCost_Input.csv](https://github.com/ShwetaGupta15/Data-Integration/files/6439489/DimProductCost_Input.csv)
- [EmployeeData_202103261432.csv](https://github.com/ShwetaGupta15/Data-Integration/files/6439491/EmployeeData_202103261432.csv)
- [IndividualCustomer_202103261439.csv](https://github.com/ShwetaGupta15/Data-Integration/files/6439492/IndividualCustomer_202103261439.csv)
- [PersonDemographics_202103261437.csv](https://github.com/ShwetaGupta15/Data-Integration/files/6439493/PersonDemographics_202103261437.csv)
- [SalesPerson_202103261440.csv](https://github.com/ShwetaGupta15/Data-Integration/files/6439494/SalesPerson_202103261440.csv)
- [StoreAddresses_202103261441.csv](https://github.com/ShwetaGupta15/Data-Integration/files/6439495/StoreAddresses_202103261441.csv)
- [StoreContacts_202103261441.csv](https://github.com/ShwetaGupta15/Data-Integration/files/6439496/StoreContacts_202103261441.csv)
- [StoreDemographics_202103261442.csv](https://github.com/ShwetaGupta15/Data-Integration/files/6439497/StoreDemographics_202103261442.csv)
- [VendorAddresses_202103261434.csv](https://github.com/ShwetaGupta15/Data-Integration/files/6439498/VendorAddresses_202103261434.csv)
- [VendorContacts_202103261435.csv](https://github.com/ShwetaGupta15/Data-Integration/files/6439499/VendorContacts_202103261435.csv)

### Target Database -
#### Srcipts for SQL Server & MySQL - [adventureWorksDW_SQL_Scripts.zip](https://github.com/ShwetaGupta15/Data-Integration/files/6439574/adventureWorksDW_SQL_Scripts.zip)














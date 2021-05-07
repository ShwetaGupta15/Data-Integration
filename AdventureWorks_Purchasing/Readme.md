## Problem Statement
This problem is the extended version of AdevntureWorks_Store_Sales where data includes new additions like -
1. Purchasing
2. Employees
3. Product

- When the bikes, bike components sold on AdventureWorks via internet or store, AdventureWorks purchases products from Vendors that they either resell or use as component in their own finished goods that they build and sell.
- The deliverables are designed to represent the Purchasing Data Warehouse, populate the tables using Talend & Alteryx into the databases MySQL & SQL Server and then to create visualizations using Tableau, PowerBI providing the belowing information-
  1. Purchases (Purchase cost & quantity) by product.
  2. Types of products purchased.
  3. Product purchased (Purchase cost & quantity) by Vendor.
  4. The Employess who were involved in purchasing and what did they purchased.
  5. Vendor's contact who were involved in purchasing and what did they purchased.

### Target Database Schema-
- All product purchase made by Adventureworks will be from Vendors, i.e. purchase orders
- List of products that might be purchased from Vendors, in other words, all the products that are not made by AdventureWorks
- Vendors that AdventureWorks might purchase products from
- Products that AdventureWorks might purchase from vendors and associated with the vendors that sell them.
- Vendors’ employees (contacts) who interact with AdventureWorks.
- Employees who have bought products from vendors and include attributes about those people such as address, email, phone, department they currently work in.
- Ship Methods
- Geography dimensions (Outrigger) that includes cities, state, countries.
- Data dimension.

#### List of Dimensions & Facts:
![image](https://user-images.githubusercontent.com/71230572/117405590-bba46880-aec0-11eb-8119-89571555843f.png)

- Schema to load dimensions and facts -
![image](https://user-images.githubusercontent.com/71230572/117406208-9ebc6500-aec1-11eb-9a16-5ad1bf8191b9.png)
![image](https://user-images.githubusercontent.com/71230572/117406272-b398f880-aec1-11eb-859a-a67ac8b1c9e2.png)
![image](https://user-images.githubusercontent.com/71230572/117406292-ba277000-aec1-11eb-8932-b78b3c2d1dd7.png)



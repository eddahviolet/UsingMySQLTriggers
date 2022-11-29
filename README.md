# UsingMySQLTriggers
Creating before and after triggers in MySQL with instructions to insert specific notifications to a notification table.

We need to implement triggers on the Products table below for Inserting, Updating and deleting any product data on the database. Create a notification table where all the update, insert and  delete actions will be recorded

![Products table](https://user-images.githubusercontent.com/106580846/204528390-01a95247-4421-4d7a-80cd-1581fa4e1640.jpg)

Task 1

Create an INSERT trigger called ProductSellPriceInsertCheck to check if the SellPrice of the product is less than the BuyPrice after a new product is inserted in the Products table. If this occurs, then a notification must be added to the Notifications table to inform the sales department. 
The notification message should be in the following format: A SellPrice less than the BuyPrice was inserted for ProductID + ProductID

![create trigger productsellpriceinsertcheck](https://user-images.githubusercontent.com/106580846/204530105-398f8634-5e46-43d2-af5c-1bddd8f8ecbe.jpg)

After creating the trigger I try to insert a new product "bushes" with a sellPrice that is less that the BuyPrice

![Inserting new record](https://user-images.githubusercontent.com/106580846/204530861-877294b1-80ed-4f9e-af6f-68f3ee96d4d7.jpg)

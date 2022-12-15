# UsingMySQLTriggers
Creating before and after triggers in MySQL with instructions to insert specific notifications to a notification table.

We need to implement triggers on the Products table below for Inserting, Updating and deleting any product data on the database. Defining the trigger name and type, and specifying the logic of a trigger by enclosing multiple statements with a BEGIN, END block. Then create a notification table where all the update, insert and  delete actions will be recorded

![Products table](https://user-images.githubusercontent.com/106580846/204528390-01a95247-4421-4d7a-80cd-1581fa4e1640.jpg)

This is adescription of the Notifications table


Task 1

Create an INSERT trigger called ProductSellPriceInsertCheck to check if the SellPrice of the product is less than the BuyPrice after a new product is inserted in the Products table. If this occurs, then a notification must be added to the Notifications table to inform the sales department. 
The notification message should be in the following format: A SellPrice less than the BuyPrice was inserted for ProductID + ProductID

![create trigger productsellpriceinsertcheck](https://user-images.githubusercontent.com/106580846/204530105-398f8634-5e46-43d2-af5c-1bddd8f8ecbe.jpg)

After creating the trigger I try to insert a new product "bushes" with a sellPrice that is less that the BuyPrice

![Inserting new record](https://user-images.githubusercontent.com/106580846/204530861-877294b1-80ed-4f9e-af6f-68f3ee96d4d7.jpg)

The trigger will create the below notification in the Notifications Table

![notification table](https://user-images.githubusercontent.com/106580846/204531281-5ee73c12-ba14-4d74-ad76-289c713684b5.jpg)

Task 2

Create an UPDATE trigger called ProductSellPriceUpdateCheck that will check that products are not updated with a SellPrice that is less than or equal to the BuyPrice. If this occurs, add a notification to the Notifications table. 
The notification message should be in the following format: ProductID + was updated with a SellPrice of  + SellPrice + which is the same or less than the BuyPrice

The trigger

![create trigger productsellpriceupdatecheck](https://user-images.githubusercontent.com/106580846/204531840-27a5c70d-84e3-4ecc-963e-f603357e2fb8.jpg)

After creating the trigger I try to update a product with the ProductID of "P6" with a sellPrice that is less that the BuyPrice

![update P6](https://user-images.githubusercontent.com/106580846/204532288-ed64516f-6270-4cef-aca2-fa0e8653930e.jpg)

The trigger will create the below notification in the Notifications Table

![notification 2](https://user-images.githubusercontent.com/106580846/204532538-3006b5f1-d642-41f8-97c8-13f3e77ff049.jpg)

Task 3

Create a DELETE trigger called NotifyProductDelete that inserts a notification in the Notifications table.

The notification message should be in the following format: The product with a ProductID  + ProductID + was deleted

The trigger

![delete trigger](https://user-images.githubusercontent.com/106580846/204535086-57fe979c-d6c0-4e84-896f-bbb64a3f2cc7.jpg)

However when I try to delete a record with ProductID "P6" it doesn't delete it, below is teh output i get, I have seen on online forums they suggest I drop the trigger which beats the purpose of the exercise in the first place

![trigger delete](https://user-images.githubusercontent.com/106580846/204536740-4d73644b-2b10-4889-bf55-4eb9286312c8.png)



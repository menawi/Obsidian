#appsheet #project_appsheet #inventory 

https://docs.google.com/spreadsheets/d/1Q9YSCgus7Ytg1u1aqQ71E0kya4ZFhgS24VKav9E6Fa8/edit#gid=0


---

> [!danger] Next Session Repairs
> 1. Add Fulfillment Table with correct number of tables
> 2. Deploy and order from phone


> Tables

1. Table "Orders" allows adds only
2. Table "Products" is _NOT_ editable

> Columns

1. Make sure to include a Product ID column in the orders table and make that the REF column , that way it will populate with product name in Google Sheets

> Views

1. Products
2. Ref Views
	1. Products Detail
	2. Order_Form
3. 

> Expressions



> Actions

1. "Order Product" = `LINKTOFORM("Orders_Form", "Product Ordered", [_THISROW])`
2. BEWARE 'system generated' actions ➡️ They were showing the "+" button on the order details page when I don't want to. For ordering, I want the user to go to products, select product, and input order


> Automations



---

> Outcome Summary


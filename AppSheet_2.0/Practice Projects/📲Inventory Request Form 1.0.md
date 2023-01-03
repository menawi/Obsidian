#project_appsheet #inventory #form

# Project Status

> [!danger] Issues to fix
> 📌 Change tables into Company (_supplier_), Customer (_clients_) and [Orders]
> 📌 Table [Orders] is a virtual table that _MUST_ be empty please
> 1. Link it to the Customer and Company table to make an order form with dropdowns


#### Function 1

Inventory order form that has 

- Dropdown orderer name
- Dropdown orderer location
- Dropdown Date wanted by

Use [[REF_ROWS]] , [[DROPDOWN_DATE]], [[UNIQUEID]]

---
#### Function 2

- Send the User a Confirmation Email
- Update the count in Inventory

---

### Functionality

# 📌 Form 
1. Choose product
	1. Dropdowns
2. Choose your customer details
	1. Dropdowns

---


### Notes

[[VLOOKUP_IMPORTRANGE]]



> [!BUG]+ ITEMS NOT VISIBLE IN UX UNLESS VIRTUAL ID COLUMN MADE

> For some reason, items are only visible on app when a virtual column is there for the item ID


> [!BUG] HOW TO CHOOSE _REF_ AND DEPENDENT COLUMNS

### Step 1 : Choose the _REF_ column 

> [!warning] THE _REF_ COLUMN (not formula REF) is the _Select Product_ column in the FORM view

## Step 2: Choose the dependend dropdowns based in _REF_


> [!warning] THE [_REF_COLUMN_].[DEPENDENT_COLUMN] ARE *INVISIBLE* in the _Select Product_ FORM view ****UNTIL**** the REF column item is selected 


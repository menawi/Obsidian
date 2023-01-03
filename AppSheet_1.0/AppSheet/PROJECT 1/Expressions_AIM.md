#AppSheet_Inventory_Management

### SELECT
#### PURPOSE : 
```javascript

// SELECT

Any(Select(stocks_inventory[item code],[_THISROW].[item name]=[item name]))

stocks_Inventory is a _table_
 item code is a column in stocks_Inventory
 AND a column in release_stocks table

 *why we using ANY ?? *

```


### ISNOTBLANK
#### PURPOSE: If the quantity here is *NOT* blank, then show it 
```javascript

This is for the "Show_If" expression in column settings

ISNOTBLANK([QUANTITY])



```

[[Expression Analysis]]
#AppSheet_Inventory_Management 

> Webhook that supposed to deduct from stocks was adding to stocks. 

Solution is adding this in the virtual columns of stocks_inventory (which he showed as if he deleted it but then acc did NOT)

## Column Name: related released stocks

### Formula: REF_ROWS("release_stocks", "item code")



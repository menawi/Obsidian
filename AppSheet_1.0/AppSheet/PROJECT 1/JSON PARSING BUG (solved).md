#AppSheet_Inventory_Management 
# Problem 

_Error 1 : Failed to parse JSON due to After parsing a value an unexpected character was encountered: :. Path 'Rows[0]', line 1, position 145.. Invalid JSON value starts with: : "1001","available stocks": "49"}]}_

## Rows[0], Line 1, Position 145

# The Invalid Values

### 1001
### available stocks
### 49

##### SOLVED !
[[API Script]]

```JSON

📌THIS IS THE CORRECT SCRIPT -- WHY?

{
"Action": "Edit",
 "Properties": {
    "Locale": "en-US",
    "Location": "47.623098, -122.330184",
    "Timezone": "Pacific Standard Time"
  },
 "Rows": [
{
"Item Code": "<<Any(Select(release_stocks[item code],[_thisrow].[item code]=[item code]))>>",
"available stocks": "<<Any(Select(release_stocks[New available stocks],[id]=MAXROW("release_stocks","_RowNumber")))>>"
}
]
}

```

##### Solution Explained

1. [itemcode] supposed to be [item code]
2. [release stocks] and _"release stocks"_ supposed to be [release_stocks] and "release_stocks"
3. [new available stocks] supposed to be [New available stocks]
4. [ID] supposed to be [id]
5. "Row Number" supposed to be "_RowNumber"


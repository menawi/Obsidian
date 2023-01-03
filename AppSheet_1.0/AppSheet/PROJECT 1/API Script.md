#AppSheet_Inventory_Management 
Script for [[Webhook]]
[Script from Video (google doc)](https://docs.google.com/document/d/1MhDbGaS9T4woFKgBGoBo43MGTmOywwRlwhBl2xqB2_4/edit?pli=1)

Specific for AppSheet API _HTTPS request task_

##### CORRECT SCRIPT HERE ⭐
[[JSON PARSING BUG (solved)]]

---

#### My Copy
# incorrect
```json
{
"Action": "Edit",
 "Properties": {
    "Locale": "en-US",
    "Location": "47.623098, -122.330184",
    "Timezone": "Pacific Standard Time"
  },
 "Rows": [
{
'item code': "<<Any(Select(release stocks[item code], [_thisrow_].[itemcode]=[itemcode]))>>",
"available stocks": Any(Select(release stocks[new available stocks],[ID]=MAXROW("release stocks"),"Row Number")))>>"
}
 ]
}

```

### Source ⭐
[[MAXROW]]
```javascript

NOTE ➡️ 🚨 ⚠️ CAREFUL , HIS NAMES ARE NOT THE SAME NAMES I HAD ⚠️ 🚨

{

"Action": "Edit",

 "Properties": {

    "Locale": "en-US",

    "Location": "47.623098, -122.330184",

    "Timezone": "Pacific Standard Time"

  },

 "Rows": [

{

"Item Code": "<<Any(Select(Release Stocks[Item Code],[_thisrow].[Item Code]=[Item Code]))>>",

"Available Stocks": "<<Any(Select(Release Stocks[New Available Stocks],[ID]=MAXROW("Release Stocks","_Rownumber")))>>"

}

]

}

```
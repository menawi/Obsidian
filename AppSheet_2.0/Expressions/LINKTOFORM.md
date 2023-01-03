#expression #appsheet 

> Difference between LINKTOFORM AND [[LINKTOVIEW]]


## Link to Another _View_

```javascript

LINKTOFORM("Orders_Form", "Date", TODAY(), "Test", [_THISROW].[Test])

⬆️ Incorrect formula ... must use link to view

```

### Example to Build off
https://www.appsheet.com/Template/AppDef?appName=LinktoformExample-31002422&appId=LinktoformExample-31002422&linkFrom=CopyApp#UX.Views.Table2_Form

```javascript

LINKTOFORM("Table2 Form", "Name2", [Name1], "Color2", [Color1])

```

> [!INFO] SYNTAX
>  LINKTOFORM( ...."Table2 Form" ...."Name2" ....The value of column 'Name1' ...."Color2" ....The value of column 'Color1'
>  
>  LINKTOFORM("Target View", "Target Entry Area", [Column Value 1], "Target Entry area 2", [Column value 2])
>  

### Practice

```javascript

LINKTOFORM("Orders Form", "Product", )

```


#sheets #formula 

Key words: #column_index #search_key #range #is_sorted

>[!BUG]+ Common Problems


> [!warning] Important Warnings
> 
> 1. VLOOKUP reads from left to right ➡️ You can't index an item to the right of the search item [why this example is ordered this way](https://docs.google.com/spreadsheets/d/1-HstedQItFJapMYgL7Wzt78PpZkhcdAs44h4mCSpNzA/edit#gid=1078489790)
> 2. 
> 


### 🪲 Out of range

> This is an _index_ problem : Make sure you select the columen index index of the _RETURN VALUE_ not the search value

---

About

Vertical lookup. Searches down the first column of a range for a key and returns the value of a specified cell in the row found.

---

## search_key

The value to search for. For example, 42, "Cats", or I24.

## range

The range to consider for the search. The first column in the range is searched for the key specified in search_key.

## index

The column index of the _value to be returned_, where the first column in range is numbered 1.

## is_sorted

Indicates whether the column to be searched (the first column of the specified range) is sorted, in which case the closest match for search_key will be returned.
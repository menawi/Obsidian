#expression 

> Query style language 

_reminds me of RStudio_

### Purpose : Gather column values from row in table or slice

Returns a list of values from the column of selected rows in the data set.

## Sample usage

```javascript

📍RETURN LIST OF ALL STUDENT FIRST NAMES - possible duplicates

SELECT(STUDENT_TABLE[first name], FALSE)

// You can also use it without the false in the end

---

📍RETURN DISTINCT STUDENT NAMES ONLY

SELECT(STUDENT_TABLE[first name], TRUE)

---

📍RETURN A LIST OF ALL STUDENTS WHO GRADUATED IN 2021

SELECT (STUDENT_TABLE[first name], ([class_of] = "2020"))

//another example

SELECT (STUDENT_TABLE[first name], ([city])="detroit", TRUE)

---

📍RETURN ALL RECORDS FOR A SPECIFIC ID

SELECT (Orders_table[order_id], ([Customer]= [_THISROW].[Customer]))

returns orders for this customer. 

More specifically, it returns the `Order ID` column values (the row keys) for rows in the `Orders` data set in which the `Customers` column value is equal to the `Customers` column value of the current form. 

Equivalent to `FILTER("Orders", ([Customer] = [_THISROW].[Customer]))`. 

`SELECT(Products[Name], ([Price] < 100), TRUE)` returns the distinct names of products priced less than $100.

```


## Syntax

```SQL
SELECT(_from-dataset-column_, _select-row?,_ [_distinct-only?_])

A relevant example ➡️ 

SELECT (LOTS_table, [Lot Number], TRUE)

```


-   `_dataset-column_` - The specification of the [table](https://support.google.com/appsheet/answer/10105821) or [slice](https://support.google.com/appsheet/answer/10106592) (the "data set") to search and the column from which values are to be gathered, in the form: `_dataset-name_[_column-name_]`. For example, `Orders[Order ID]`. Although identical in appearance to a column list expression, this argument is not an expression.
-   `_select-row?_` -  A `Yes/No` expression, evaluated for each row of the data set, that returns `TRUE` or `FALSE` indicating whether the column value from the row should be included (`TRUE`) or excluded (`FALSE`) in the results.
-   `_distinct-only?_` - A `Yes/No` expression. Set to `FALSE` to indicate the results list should include all values found in selected rows, or `TRUE` to indicate duplicate values should be omitted. If not given, `FALSE` is assumed.

### Troubleshoot

Within the second argument, the _`select-row?`_ expression, 

⚠️ __any column references are interpreted from the perspective of the data set being searched, not that of the data set from which the expression is run__ ⚠️.

In order to reference columns from the current row, you must [dereference](https://support.google.com/appsheet/answer/10107396) `_THISROW`.


For example, consider this attempt from an order row to get the item descriptions from the order detail rows:

```javascript

SELECT(Order Details[Description], ([Order ID] = [Order ID]), TRUE)

```

The goal is to __select rows from the `Order Details` data set with an `Order ID` column value that matches this order's own ID.__ But within the _`select-row?`_ expression (`([Order ID] = [Order ID])`), both column references refer to the `Order Details` row being examined. 

As written, the expression will always be `TRUE`.

To reference a column of the current row, dereference `_THISROW` to get the desired column:

```javascript

SELECT(Order Details[Description], ([Order ID] = [_THISROW].[Order ID]), TRUE)


---

SELECT(Student_Table[firstnames], ([student_id] = [_THISROW].[student_id]), TRUE)

In English : `Search ${Student_Table} using ${'student_id'} from this table and match it to that table`

---

📍practice e.g

` select all student ${firstnames} using their ${student_id} in this table and return all the ones that ${graduated in 2021} `

SELECT(student_table[firstnames], ([student_id] = [_THISROW].[student_id]), TRUE)



```

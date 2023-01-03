#expression 

# Row with greatest value in column

Returns the [key](https://support.google.com/appsheet/answer/10108207) of a row (`Ref` value) in the data set that contains the maximum value found in the named column from among the rows selected by an expression, or from among all rows if an expression was not provided.

## Sample usage

### `MAXROW("Products", "Discount")` returns the key value for the row in the `Products` data set that has the highest value in the `Discount` column (that is, which product has the greatest discount?). 

Equivalent to `MAXROW("Products", "Discount", TRUE)`.

`MAXROW("MyTable", "_ROWNUMBER")` returns the key value for the row in the `MyTable` data set that has the highest value in the `_ROWNUMBER` column (that is, which row was added last?).

`MAXROW("Students", "GPA", ([Class] = "2018"))` returns the row for the (one) student with the highest GPA of the class of 2018.

`MAXROW("Sales", "Close Date", ([City] = "Madrid"))` returns the row for the newest sale in Madrid.

`MAXROW("Events", "Date", ([Date] < [_THISROW].[Date]))` returns the row for the most recent preceding event.

`MAXROW("Events", "Date", ([Date] < DATE("1/1/" & YEAR(TODAY()))))` returns the row for the most recent event prior to this year. See also: `[DATE()](https://support.google.com/appsheet/answer/10107957)`, `[TODAY()](https://support.google.com/appsheet/answer/10108286)`, `[YEAR()](https://support.google.com/appsheet/answer/10107427)`

`MAXROW("MyTable", "SomeColumn", FALSE)` : returns a blank value because the `select-row?` expression will always return FALSE, excluding all rows from the search.

### Common Problems

`MAXROW(Events, Date)` produces the error, `Expression [...] could not be parsed due to exception: #VALUE!`_._ In this example, the column name, `Date`, has significance within the internals of AppSheet and causes confusion. Any data set name that matches an AppSheet or Excel function name may produce this problem. To fix, quote the problem name: `MAXROW(Events, "Date")`

`MAXROW("Events", "Date", ([Venue] = [Wanted Venue]))` produces the error, `Unable to find column [...]`. Column references within the `select-row?` expression (such as, `[Venue]`) are to the row being considered as the data set is searched. To access columns outside the row being considered, such as when using `MAXROW()` from within a column constraint, app formula, initial value, or format rule, reference the external column using `_THISROW`: `MAXROW("Events", "Date", ([Venue] = [_THISROW].[Wanted Venue]))`

## Syntax

`MAXROW(_dataset_, _column,_ [_select-row?_])`

-   _`dataset`_ - Name of the [table](https://support.google.com/appsheet/answer/10105821) or [slice](https://support.google.com/appsheet/answer/10106592) (the "data set") to search as a literal `Text` value (quoted or unquoted); may not be an expression.
-   `_column_` - Name of the column of the named data set in which to find the maximum value, as a literal `Text` value (quoted or unquoted); may not be an expression.
-   `_select-row?_` - An optional `Yes/No` expression, evaluated for each row of the data set, that returns `TRUE` or `FALSE` indicating whether the row should be included (`TRUE`) or excluded (`FALSE`) in the search for the maximum value. If no expression is provided, all rows of the data set will be searched (equivalent to the expression, `TRUE`).

## Notes

If the column maximum was found in more than one row, one of the maximum rows will be chosen at random.

## See also

`[FILTER()](https://support.google.com/appsheet/answer/10108196)`

`[MAX()](https://support.google.com/appsheet/answer/10107969)`

`[MINROW()](https://support.google.com/appsheet/answer/10107414)`

`[ORDERBY()](https://support.google.com/appsheet/answer/10107362)`

`[REF_ROWS()](https://support.google.com/appsheet/answer/10107364)`

`[SELECT()](https://support.google.com/appsheet/answer/10108207)`
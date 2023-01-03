#appsheet #expression 


Write an expression to get a value from a specific column and row

Column value expressions return the value of a specific column in a row. The row itself does not need to be specified; it's usually implicit in the context of the expression.

-   Name any column using square brackets around the exact column name: `[ColumnName]`.
-   When used in a [column constraint](https://support.google.com/appsheet/answer/10107948) (`[Editable_If](https://support.google.com/appsheet/answer/10107954)`,  `[Required_If](https://support.google.com/appsheet/answer/10106535)`, `[Show_If](https://support.google.com/appsheet/answer/10106628)`, or `[Valid_If](https://support.google.com/appsheet/answer/10107949)`), you can use `[_THIS]` to refer to the value of the current column of the current row.
-   If the current row is not implicit from the context of the expression, it must be explicitly specified using a [dereference expressions](https://support.google.com/appsheet/answer/10107396)

**New to expressions and formulas?** See [Expressions: The Essentials](https://support.google.com/appsheet/answer/10104642).

## Common use cases

-   In a [virtual column](https://support.google.com/appsheet/answer/10106758): `CONCATENATE([FirstName], " ", [LastName])`
-   In a [slice filter condition](https://support.google.com/appsheet/answer/10106308): `[Status] = "Complete"`
-   In a [Valid_If column constraint](https://support.google.com/appsheet/answer/10107949): `[_THIS] > 25`


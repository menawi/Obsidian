#ID 

# [What is a key?](https://support.google.com/appsheet/answer/10106672?visit_id=638071750114024723-586269696&p=key&rd=1#types)

A key uniquely identifies each row in a table.

When you add a row to a table, that row must have a unique key value. 

The row's key value must remain constant for the life of the row.

When you update or delete a row through an AppSheet app, the key is used to find the row to update or delete.

If two or more rows are inadvertently assigned the same key value, we say the table contains "duplicate keys". This is a serious problem. If someone attempts to update or delete one of these rows, the wrong row may be updated or deleted.

## Types of keys

AppSheet supports three types of keys. From best to worst, these key types are:

-   [Natural keys](https://support.google.com/appsheet/answer/10106672?visit_id=638071750114024723-586269696&p=key&rd=1#natural-keys)
-   [System-generated keys](https://support.google.com/appsheet/answer/10106672?visit_id=638071750114024723-586269696&p=key&rd=1#system-generated-key)
-   [Row number keys](https://support.google.com/appsheet/answer/10106672?visit_id=638071750114024723-586269696&p=key&rd=1#row-number-key)

The following sections provide more information about keys:

-   [Types of keys](https://support.google.com/appsheet/answer/10106672?visit_id=638071750114024723-586269696&p=key&rd=1#types)
-   [Select a key](https://support.google.com/appsheet/answer/10106672?visit_id=638071750114024723-586269696&p=key&rd=1#select)
-   [Column types that can't be used as the key](https://support.google.com/appsheet/answer/10106672?visit_id=638071750114024723-586269696&p=key&rd=1#unsupported-column-types)


### Natural keys

Many tables have a Natural key, a single field or a combination of fields that uniquely identify each table row.

> So the "fields" of a record for example "SKU", "Description", "LOT"

Your table may often have a single field containing a value that uniquely identifies each row. For example, an `Employee` table may contain an `EmployeeID` field that contains a unique employee ID. When such a field is present, it makes an ideal key.

#### Natural multi-column keys

Your table may contain two or more fields that together contain values uniquely identifying each row. 

For example, a `Vehicle` table may contain a `State` field and a `LicensePlateNumber` field that together uniquely identify each row. 

A multi-column key is slightly more *unwieldy* than a single column key, but it makes an excellent key.

> unwieldy : *difficult to carry or move because of its size, shape, or weight.

#### Natural computed keys

Your table may contain fields that can be combined to yield a #unique computed key value. The row's computed key value must remain #constant for the life of the row.

You specify the key computation expression in the key field's [app formula property](https://support.google.com/appsheet/answer/10106437).

The editor examines this expression to ensure that it yields the same result over time, and displays an error if it does not. 

For example, an app formula that includes the current date or time might yield different results over time, so it would be prohibited in a key field's app formula.

#### Why not worksheet formulas?

In a spreadsheet, it's sometimes convenient to have an ID column that is computed with a worksheet formula. 

For example, the worksheet formula might increment the value in the previous row. This does not work for AppSheet table keys for two reasons. 

First, keys must be unique and unchanging over time, but that is not possible to guarantee with worksheet formulas. 

Second, it must be possible to compute the formula when the app is working offline, but that is not possible with worksheet formulas.

#unique #constant #offline

> Record keys must be #unique #constant and available #offline 

#### Sequential keys

We are often asked if there is a way for AppSheet to generate sequential, unique keys starting from a user specified initial value. 

#sequential  means there must be no gaps in the key sequence. 

For example, the values `INV01000`, `INV01001`, and `INV01002`, are sequential. Ideally the sequential keys should be issued in order of record creation time.

Unfortunately in a distributed system, with multiple users, and offering offline data inserts, it's technically impossible to generate identifiers satisfying all of these requirements. That is true whether the generated value is used as a key value or as a normal field value.

	You can use a `[MAX()](https://support.google.com/appsheet/answer/10107969)` expression to generate sequential unique key values; however, this only works when a single user adds records. For example, you might use the expression `MAX(Orders[OrderNumber])+1` to generate a sequential `OrderNumber` key value for the `Orders` table. It's very risky to use such an expression to generate a key value when more than one user can add records, because the computed key values may not be unique.


#### Random keys

One alternative to system-generated sequential keys, is system-generated random keys.

AppSheet currently supports two mechanisms for creating system-generated random keys.

-   The `[UNIQUEID()](https://support.google.com/appsheet/answer/10108209)` function generates a 8-character long unique text value containing letters and numbers.
-   The `[RANDBETWEEN(lower-bound, upper-bound)](https://support.google.com/appsheet/answer/10107982)` function generates a pseudo random numeric value between `lower-bound` and `upper-bound`.

Because these functions generate pseudo random values, they do not require coordination between the clients and the server. They work for multiple users doing offline inserts.

[[UNIQUEID]]
[[RANDINBETWEEN]]


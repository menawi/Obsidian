#appsheet 

## ANY()

> In the video I was watching, it was used with [[SELECT]]

Returns an item from a list, as follows:

1.    The first item from a list if it is _constructed_ (for example, using `[LIST()](https://support.google.com/appsheet/answer/10107339)`).

2.    _An arbitrary item if a list is a generated list (for example, using `[FILTER()](https://support.google.com/appsheet/answer/10108196)` or `[SELECT()](https://support.google.com/appsheet/answer/10108207)`)._
> This is it here 

%% what is filter? %%

3.  Blank if the list is empty.

**Note**: The order of the list cannot be guaranteed unless wrapped in `[SORT()](https://support.google.com/appsheet/answer/10107698)`.


**Why it is important**

ANY might not be selective on its own, but combined with [[SELECT]] for example, it can be very powerful.

# Common problems

`ANY(1, 2, 3)` : the arguments are not in list form. To fix, wrap them in `[LIST()](https://support.google.com/appsheet/answer/10107339)` to construct a list: `ANY(LIST(1, 2, 3))`.

## Syntax

`**ANY(**_list_**)**`

-   `_list_` - List of any type.

## Sample usage

`ANY(Students[Name])` returns an arbitrary value from the `Name` column of the `Students` table. 


```javascript

ANY(SELECT[NAME])

const student_table = {
        mark { name: 'mark', class: 2020},
        jane{ name: 'jane', dob: 2020 },
        phil{name: 'phii'}, dob: 2019}
}

*result* : {jane}

ANY(SELECT[NAME], ([class] = "2020" ))

*result* : returns name of a random select of someone of class "2020"




```

Arbitrary because the order of values in the `Students[Name]` column list isn't guaranteed unless wrapped in [`SORT()`](https://help.appsheet.com/expressions/functions/sort). 

Equivalent to `ANY(SELECT(Students[Name], TRUE))`. 

See also: `[SELECT()](https://support.google.com/appsheet/answer/10108207)`

```javascript

ANY(LIST(1, 2, 3)) returns 1 (Number)

ANY({"Red", "Yellow", "Green"}) returns 'Red' (Text)

Column value

A single column value from any of a set of rows:

```


ANY(SELECT(Products[Price], ([Color] = "Orange")))

1.  `SELECT(Products[Price], ...)` returns values in the `Price` column from rows in the `Products` table that match the selection criteria.
2.  `[Color] = "Orange"` limits the selection to only those rows with a `Color` column value of exactly `Orange`.
3.  `ANY(...)` returns one arbitrary value from the list of column values.

Equivalent to: `LOOKUP("Orange", "Products", "Color", "Price")`

See also: `[LOOKUP()](https://support.google.com/appsheet/answer/10107410)`, `[SELECT()](https://support.google.com/appsheet/answer/10108207)`

### Highest value in column

The highest product price:

```
ANY(TOP(SORT(Products[Price], TRUE), 1))
```

1.  `Products[Price]` retrieves the list of all values from the `Price` column of the `Products` table.
2.  `SORT(..., TRUE)` orders the list of prices numerically in descending/high-to-low order (`TRUE`).
3.  `TOP(..., 1)` removes all but the first price in the sorted list.
4.  `ANY(...)` returns the one remaining price from the top list.
5.  Equivalent to `MAX(Products[Price])`.

Equivalent to `MAX(Products[Price])`.

See also: `[MAX()](https://support.google.com/appsheet/answer/10107969)`, `[SORT()](https://support.google.com/appsheet/answer/10107698)`, `[TOP()](https://support.google.com/appsheet/answer/10107704)`

### Preferred value

A mobile, office, or home phone number chosen from those that aren't blank:

```
ANY(
  TOP(
    (
      LIST([Mobile Phone], [Office Phone], [Home Phone])
      - LIST("")
    ),
    1
  )
)
```

1.  `LIST([Mobile Phone], [Office Phone], [Home Phone])` constructs a list of the three numbers.
2.  `LIST(...) - LIST("")` removes any blank items from the list of numbers.
3.  `TOP(..., 1)` removes all but the first from the list of non-blank numbers.
4.  `ANY(...)` returns the only remaining non-blank number from the top list.

Equivalent to:

```
INDEX(
  (
    LIST([Mobile Phone], [Office Phone], [Home Phone])
    - LIST("")
  ),
  1
)
```

See also: `[LIST()](https://support.google.com/appsheet/answer/10107339)`, `[INDEX()](https://support.google.com/appsheet/answer/10107336)`, `[TOP()](https://support.google.com/appsheet/answer/10107704)`

### Row with highest value in column

The row of the student with the highest GPA in Mr Sandwich's class:

```
ANY(
  TOP(
    ORDERBY(
      FILTER("Students",
        AND(
          ISNOTBLANK([Teacher]),
          ([Teacher] = "Mr Sandwich")
        )
      ),
      [GPA], TRUE
    ),
    1
  )
)
```

1.  `FILTER("Students", ...)` returns a list of key values from the `Students` table that match a condition.
2.  `AND(..., ...)` limits the filter to only those rows that match all of the given sub-conditions.
3.  `ISNOTBLANK([Teacher])` requires the `Teacher` column value not be blank.
4.  `[Teacher] = "Mr Sandwich"` requires the `Teacher` column value be exactly `Mr Sandwich`.
5.  `ORDERBY(..., [GPA], TRUE)` orders the filtered keys by the values of their corresponding `GPA` column value in descending/high-to-low order (`TRUE`), putting high GPAs first.
6.  `TOP(..., 1)` removes all but the first item in the ordered list, leaving only the key of the row having the highest GPA.
7.  `ANY(...)` returns the one remaining entry from the top list: the key of the row corresponding to the student with the highest GPA in Mr Sandwich's class.

Equivalent to:

```
MAXROW(
  "Students", "GPA",
  AND(
    ISNOTBLANK([Teacher]),
    ([Teacher] = "Mr Sandwich")
  )
)
```

See also: `[AND()](https://support.google.com/appsheet/answer/10107398)`, `[FILTER()](https://support.google.com/appsheet/answer/10108196)`, `[ISNOTBLANK()](https://support.google.com/appsheet/answer/10107964)`, `[ORDERBY()](https://support.google.com/appsheet/answer/10107362)`, `[MAXROW()](https://support.google.com/appsheet/answer/10107920)`, `[TOP()](https://support.google.com/appsheet/answer/10107704)`



## See also

`[INDEX()](https://support.google.com/appsheet/answer/10107336)`

`[TOP()](https://support.google.com/appsheet/answer/10107704)`
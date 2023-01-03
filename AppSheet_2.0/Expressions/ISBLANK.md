#expression 

## Intro
> Is value absent?

_Returns a `Yes/No` expression, as follows:

-   `TRUE` if the specified item has no value. (An empty list has no value.)
    
-   `FALSE` if the specified item has a value.
    


## Sample usage

`ISBLANK("")` returns `TRUE`

`NOT(ISBLANK(""))` returns `FALSE`. Equivalent to `ISNOTBLANK("")`. See also: `[ISNOTBLANK()](https://support.google.com/appsheet/answer/10107964)`.

`ISBLANK("Hi!")` returns `FALSE`

`ISBLANK(0)` returns `FALSE`

`ISBLANK(LIST())` returns `TRUE`. See also: `[LIST()](https://support.google.com/appsheet/answer/10107339)`

`ISBLANK(LIST("Red", "Yellow", "Green"))` returns `FALSE`

#### Examples

##### CHECK IF ANY ROWS IN COLUMN "ADDRESS"

```javascript

ISBLANK([ADDRESS]) 

// if one address row is empty

*result* : TRUE


```

##### CHECK IF ANY CUSTOMERS ARE IN LONDON

```javascript

// ISBLANK(FILTER([CUSTOMER_CITY], ([CUSTOMER_ADDRESS] = "LONDON"))) *wrong ??*

ISBLANK(FILTER("Customers", ([City] = "London")))

		➡️  returns `TRUE` if no customers are in London. *correct !! *



```

`ISBLANK([Address])` returns `TRUE` if the `Address` column has no value, `FALSE` otherwise. Equivalent to `("" = [Address])` (but not to `([Address] = "")`. as described in Common problems, below).

`ISBLANK(FILTER("Customers", ([City] = "London")))` returns `TRUE` if no customers are in London. 

Equivalent to `(COUNT(FILTER("Customers", ([City] = "London"))) = 0)`. See also: `[COUNT()](https://support.google.com/appsheet/answer/10107676)`, `[FILTER()](https://support.google.com/appsheet/answer/10108196)`

### Common problems

`ISBLANK([Address])` is not equivalent to `([Address] = "')` because the is-equal-to operator (`=`) will always return `TRUE` if the second operand is a blank value, regardless of the first operator. Swapping the operands (for example, `("" = [Address])`) works around this behavior.

## Syntax

`ISBLANK(_value_)`

-   `_value_` - Any singular value of any type, or a list of any type.

## See also

`[ISNOTBLANK()](https://support.google.com/appsheet/answer/10107964)`
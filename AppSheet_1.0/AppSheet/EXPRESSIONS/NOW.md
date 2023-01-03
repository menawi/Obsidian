#expression 

> _I usually use the DATE(NOW()) expression to isolate the date aspect of NOW().
You can also use TIME(NOW()) to isolate the time aspect. 
If you want the full date and time of today, use NOW()_


## Returns the current date and time (`DateTime` value).

### Sample usage

#### The "+/-days" usage

>Days, Weeks, Months
`(NOW() - 1)` returns the date and time one day in the past. Equivalent to `(NOW() - "024:00:00")`.
	`(NOW() + 1)` returns the date and time one day in the future.
	`(NOW() + 7)` returns the date and time one week in the future.
__`DATE(NOW())` returns the current date as a `Date` value. Equivalent to `TODAY()`.__ 
	See also: `[DATE()](https://support.google.com/appsheet/answer/10107957)`, `[TODAY()](https://support.google.com/appsheet/answer/10108286)`
`TIME(NOW())` returns the current time. Equivalent to `TIMENOW()`. See also: `[TIME()](https://support.google.com/appsheet/answer/10107367)`_,_ `[TIMENOW()](https://support.google.com/appsheet/answer/10107985)

##### Example 

 ```javascript

When ${expiration date} is <= 30 days from NOW(), then send warning SMS and Email to [${user_1}, ${user_2}]

if ("expiry" - DATE(NOW()) <= 30 ), {
send "`${item_name} is going to expiry in 30 days` "
} esle { }

 ```


## Syntax

`NOW()`

## Notes

The values returned by `NOW()`, `TODAY()`, and `TIMENOW()` reflect the timezone offset of the user's device. For example, if the timezone of the user's device is Pacific Standard Time (PST), the value returned is UTC-08:00; if the timezone of the user's device is Hong Kong, the value returned is UTC+8:00.

When the user's device contacts the server to read or update data, the device includes its timezone with the request. The server uses the timezone of the user's device when performing time and date calculations. For example, when the server evaluates security filters and workflow rules that include dates and times.

For information about the locale, see [Apps using Date, Time, and DateTime formats](https://support.google.com/appsheet/answer/10106702).

## See also

[Date and time expressions](https://support.google.com/appsheet/answer/10107326)

`[DATE()](https://support.google.com/appsheet/answer/10107957)`

`[TIME()](https://support.google.com/appsheet/answer/10107367)`

`[TIMENOW()](https://support.google.com/appsheet/answer/10107985)`

`[TODAY()](https://support.google.com/appsheet/answer/10108286)`
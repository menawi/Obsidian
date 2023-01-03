#sheets #formula 

> [!INFO] Confirm if a UNIQUE column is indeed Unique
> Important to confirm if Order [[UNIQUEID]] is unique and valid

```javascript

= IF((A2:A1000 = UNIQUE(A2:A1000)), TRUE, FALSE)

```


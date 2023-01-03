#columns 
## Important to dis-ambiguate the records

AppSheet may automatically generate a key based on 

1. The left most column (_RowNumber_ for example) or the _Item Code_ column
2. Combine 2 Columns 

## Best practice

Use a separate _real_ (as opposed to *virtual* column) and add a [[UNIQUEID]] expression in it

#### Put UNIQUEID() in the _initial value_ area


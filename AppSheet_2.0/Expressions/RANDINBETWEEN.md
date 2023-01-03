#expression #formula 

```javascript

RANDINBETWEEN(lower, upper)

e.g. RANDBETWEEN(1,99999999)


```


> [!success] Generate random letters and characters #1
> 

```javascript

= CHAR(RANDBETWEEN(65,90))

```


> [!SUCCESS] Generate random letters and characters #2

```javascript

=CONCATENATE(CHAR(RANDBETWEEN(1,1000)), CHAR(RANDBETWEEN(2,2000)))

let result = ["Ӹ", "ɡф", "etc etc"]

```


> [!success] Generate random letters and characters # CRACKED formula

```javascript

= CHOOSE(RANDBETWEEN(1,2),CHAR(RANDBETWEEN(65,90)),                         
		
		CHAR(RANDBETWEEN(97,122)))&
 
 CHOOSE(RANDBETWEEN(1,2),CHAR(RANDBETWEEN(65,90)),

		CHAR(RANDBETWEEN(97,122)))  

let result = ["yW", "hi", "sZ"]


```

=CHOOSE(RANDBETWEEN(1,2),CHAR(RANDBETWEEN(65,90)),                  CHAR(RANDBETWEEN(97,122)))CHOOSE(RANDBETWEEN(1,2),CHAR(RANDBETWEEN(65,90)),CHAR(RANDBETWEEN(97,122))) 


> [!TIP] Template to Generate a random Unique ID

#formula_snipped

```javascript

// Run once
= RANDBETWEEN(99999999,99999999999)

// Run 3 times
= CHOOSE(RANDBETWEEN(1,2),CHAR(RANDBETWEEN(65,90)), CHAR(RANDBETWEEN(97,122)))& CHOOSE(RANDBETWEEN(1,2),CHAR(RANDBETWEEN(65,90)), CHAR(RANDBETWEEN(97,122)))

// Conctenate them


```
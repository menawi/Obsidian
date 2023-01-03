#expression 

```javascript

#Formula
SWITCH(USEREMAIL(), 
  "user1@mydomain.com", "UPDATES_ONLY", 
  "user2@mydomain.com", "ALL_CHANGES", 
  "READ_ONLY")

#Allowed_Values
An expression to dynamically change the update mode of the table on a per-user basis. The allowed values are "READ_ONLY", "UPDATES_ONLY", "ADDS_ONLY", "ADDS_AND_UPDATES", "DELETES_ONLY", "UPDATES_AND_DELETES", "ADDS_AND_DELETES", and "ALL_CHANGES" (Enum)

📌example 

SWITCH(
	USEREMAIL(
	"omar.elmenawi@flowhealth.com", "ALL_CHANGES",
	"andrew.underhill@flowhealth.com", "ADDS_AND_DELETES" )
	)


```


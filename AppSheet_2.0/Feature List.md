#appsheet #expression 

---
[Feature Sample List Link](https://support.google.com/appsheet/answer/13036033?hl=en&ref_topic=11981018) ⭐
[[Expressions 2.0]]

##  [Activity Schedule](https://www.appsheet.com/Template/AppDef?appName=ExtracurricularSchedule-71626&appId=ExtracurricularSchedule-71626#Data.Columns.Activity_Schema)

Learned how to incorporate the [[DROPDOWN_DATE]] function based on their 

```Javascript

@(_TIMENOW)

```

##  [Dependent Dropdown](https://www.appsheet.com/Template/AppDef?appName=DependentDropdowns-71626&appId=DependentDropdowns-71626#Data.Columns.Comments_Schema)

- The example is really not the best.
- The main point here is that some columns are _restricted_ by REF and by Data Validity to Choose from certain columns
- Main use is in _form_ view


## [Distinct Pairs](https://www.appsheet.com/Template/AppDef?appName=ItemCharacteristics-71626&appId=ItemCharacteristics-71626#UX.Views.Items)

> ❓ _Don't understand this_


## [Distinct value dropdown](https://www.appsheet.com/Template/AppDef?appName=Onlyallowdistinct-71626&appId=Onlyallowdistinct-71626#Data.Tables)

> ❓ _Don't understand how to do this yet_

```javascript
This is the "Validity" formula

Equipment[Name] -
SELECT(Request[Equipment], [Timestamp] <> [_THISROW].[Timestamp])
```

# [Dropdowns](https://www.appsheet.com/Template/AppDef?appName=Dropdowns-71626&appId=Dropdowns-71626#Data.Columns.Ref%20Values_Schema)


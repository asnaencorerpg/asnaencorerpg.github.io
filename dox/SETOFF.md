---
title: SETOFF

Id: SETOFF
TocParent: aerLrfOpCodesMain
TocOrder: 1480


---

Sets the indicators specified in the resulting indicators OFF.

```
SETOFF 
Hi (Indicator Variable)
Lo (Indicator Variable)
Eq (Indicator Variable)
IndList (Indicator Variable, Indicator Variable, ...)
```

### Parameters

**Hi** 

Optional. Sets off the Hi resulting indicator variable.


**Lo** 

Optional. Sets off the Lo resulting indicator variable.


**Eq** 

Optional. Sets off the Eq resulting indicator variable.


**IndList** 

Optional. Allows you to specify all of the resulting indicators, separated by commas.


### Remarks
You can set off any combination of the resulting indicators, or you can specify all of them using the **IndList** parameter. 

### Example

```
DclFld NotFoundIndicator *Ind
SETOFF *In50        
SETOFF NotFoundIndicator

    -or-

*In50 = *Off
NotFoundIndicator = *Off
```

### See Also
[SETON](SETON.html) 

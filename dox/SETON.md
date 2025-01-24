---
title: SETON

Id: SETON
TocParent: aerLrfOpCodesMain
TocOrder: 1490


---

Sets the indicators specified in the resulting indicators ON.

```
SETON 
Hi (Indicator Variable)
Lo (Indicator Variable)
Eq (Indicator Variable)
IndList (Indicator Variable, Indicator Variable, ...)
```

### Parameters

**Hi** 

Optional. Sets on the Hi resulting indicator variable.


**Lo** 

Optional. Sets on the Lo resulting indicator variable.


**Eq** 

Optional. Sets on the Eq resulting indicator variable.


**IndList** 

Optional. Allows you to specify all of the resulting indicators, separated by commas.


### Remarks
You can set on any combination of the resulting indicators, or you can specify all of them using the **IndList** parameter. 

### Example

```
DclFld NotFoundIndicator *Ind
Seton *In50
 SETON NotFoundIndicator

-or-

*In50 = *On
NotFoundIndicator = *On
```

### See Also
[SETOFF](SETOFF.html) 

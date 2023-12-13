---
title: ENDSL

Id: ENDSL
TocParent: aerLrfOpCodesMain
TocOrder: 920


---

Ends a [SELECT](SELECT.html) group.

```
ENDSL 
        
```

### Remarks
Conditioning indicators are not allowed. 

### Example

```
Select
   When X = 1
   B = A + B
   Exsr UpdateMaster
   When X < 10 *and Y = 2
   B = B - A
   Other
   Exsr ErrorRoutine
 EndSL 
```

### See Also
[SELECT](SELECT.html)

[WHEN](WHEN.html) 

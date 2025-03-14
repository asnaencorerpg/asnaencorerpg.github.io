---
title: ENDENUM

Id: ENDENUM
TocParent: aerLrfOpCodesMain
TocOrder: 820


---

Finishes an [Enumeration](/concepts/EnumerationsOverview.html) definition ([BEGENUM](BEGENUM.html)). 

```
ENDENUM 
        
```

### Remarks
An **ENDENUM** finishes an Enumeration definition.

### Example

```
BegEnum myEnum basetype( *byte )
   DclEnumFld q4 value(4)   // <--- the default value is 0
   DclEnumFld q5            // <--- this will be 5, which is 1 plus the previous one
 **EndEnum** 
```

### See Also
[BEGENUM](BEGENUM.html)

[Enumeration Definition](/concepts/EnumerationsOverview.html) 

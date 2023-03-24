---
title: ENDGET

Id: ENDGET
TocParent: aerLrfOpCodesMain
TocOrder: 850


---

Terminates a [BEGGET](BEGGET.html) procedure.

```
 **ENDGET**       
```

### Remarks
An ``` **ENDGET** ``` routine **must** begin with a ``` **BEGGET** ```. 

### Example

```
BEGPROP Prop1 Type(*Integer) Len(4) Access(*Public)
   BEGGET
    LeaveSR 5
 ENDGET BEGSET NewValName (MyName)
     C = A * B
     zero[1] = D
   ENDSET
ENDPROP
```

### See Also
[BEGGET](BEGGET.html)
[BEGSET](BEGSET.html)
[ENDSET](ENDSET.html) 

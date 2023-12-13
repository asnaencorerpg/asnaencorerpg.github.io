---
title: ENDINTERFACE

Id: ENDINTERFACE
TocParent: aerLrfOpCodesMain
TocOrder: 870


---

Ends a [BEGINTERFACE](BEGINTERFACE.html) interface definition.

```
ENDINTERFACE 
        
```

### Remarks
An **ENDINTERFACE** marks the end of a **BEGINTERFACE** interface definition. 

### Example

```
 //Define an Interface BegInterface **myInterface** 
  BegSr Customer
    DclSrParm Name *integer4
  EndSr

  BegFunc Function Type( *integer4 )
  EndFunc
  DclEvent EVENT type( System.EventHandler )
 EndInterface // Interface Usage BegClass Overloaded Access (*Public) Implements( **myInterface**  )
  BegSr First Access (*Public) implements ( myInterface.Customer )
    DclSrParm theParm *interger4
  EndSr
```

### See Also
[BEGINTERFACE](BEGINTERFACE.html) 

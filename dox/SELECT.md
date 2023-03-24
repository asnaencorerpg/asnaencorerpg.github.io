---
title: SELECT

Id: SELECT
TocParent: aerLrfOpCodesMain
TocOrder: 1420


---

Conditionally processes one of several alternative sequences of operations. It consists of a **SELECT** statement, zero or more [WHEN](WHEN.html) groups, an optional [OTHER](OTHER.html) group, and an [END](END.html) or [ENDSL](ENDSL.html) statement. 

```

 **SELECT** 
        
```

### Remarks
The **SELECT** group can be specified anywhere in calculations. It can be nested within [IF](IF.html) and [DO](DO.html) select groups. The **IF** and **DO** groups can also be nested within **SELECT** groups. 

### Example
/* In this example, if X equals 1, do the operations in sequence 1 (note that no **END** operation is needed before the next WHEN); if X does NOT equal 1, and if Y=2 and X<10, do the operations in sequence 2. If neither condition is true, do the operations in sequence 3. */ 

```

 **SELECT** 
    When X = 1 
    B = A + B 
    ExSR UpdateMaster
    When X < 10 *and Y = 2
    B = B - A
    Other
    ExSR ErrorRoutine
 EndSL
```

/* This example shows a **SELECT** group with conditioning indicators. After the ReadRand operation, if indicator 10 is on, then control passes to the ADD operation. If indicator 10 is off, then the **SELECT** group is processed. */ 

```
ReadRand ItemFile ItemKey NotFnd(*In10)
If *In10 = *Off
 **SELECT** 
    When X = 1
    B = B + Q
    ExSR Update NewOrder
    When X = 2
    ExSR NewOrderForm
  EndSL
EndIf
```

### See Also
[END](END.html)
[ENDSL](ENDSL.html)
[IF](IF.html)
[OTHER](OTHER.html) 

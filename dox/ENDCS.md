---
title: ENDCS

Id: ENDCS
TocParent: aerLrfOpCodesMain
TocOrder: 800


---

Ends a [CASE](CASE.html) operation.

```

 **ENDCS** 
        
```

### Remarks
Conditioning and resulting indicators are not allowed.

### Example

```
Case 
   (OnHand = OnOrder) Sr(CutOrder)
    CaseDft Sr(ReviewOrder)
//The **Endcs**  operation denotes the end of the Case group.
 Endcs 
```


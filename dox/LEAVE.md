---
title: LEAVE

Id: LEAVE
TocParent: aerLrfOpCodesMain
TocOrder: 1170


---

Control is transferred from within a loop to the statement following the [END](END.html) operation. 

```
LEAVE 
        
```

### Remarks
**LEAVE** causes control to transfer "outwards" by one level only in nested loops. **LEAVE** is not allowed without a **DO** group. 

**LEAVE** is similar to the [ITERATE](ITERATE.html) operation, however **ITERATE** transfers control to the loop's **END** command. 

### See Also
[DO](DO.html)

[DOUNTIL](DOUNTIL.html)

[DOWHILE](DOWHILE.html)

[END](END.html)

[ITERATE](ITERATE.html) 

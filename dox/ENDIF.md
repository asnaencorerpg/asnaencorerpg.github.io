---
title: ENDIF

Id: ENDIF
TocParent: aerLrfOpCodesMain
TocOrder: 860


---

Ends an [IF](IF.html), or [ELSE](ELSE.html) group.

```

        ```<span style="FONT-WEIGHT: bold">ENDIF</span>```
        
```

### Remarks
```ENDIF``` must be the last statement within a subroutine that is preceded with an ```IF```, or ```ELSE``` group. 

### Example

```
If 
   *In17 = *On
   Do 1 10 X
   Y = Y + 1
   Enddo
 Endif 
```

### See Also
[ELSE](ELSE.html)

[IF](IF.html) 

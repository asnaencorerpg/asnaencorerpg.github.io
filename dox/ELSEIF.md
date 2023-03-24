---
title: ELSEIF

Id: ELSEIF
TocParent: aerLrfOpCodesMain
TocOrder: 760


---

**ELSEIF** is similar to ELSE, except that it allows a condition to be tested if the previous conditional test (IF or **ELSEIF** ) has failed. **ELSEIF** provides a more succinct way of doing nested IFs. 

```

 **ELSEIF** 
 **Cond**  (Condition Expression)
```

### Parts

**Cond** 

Required. The condition to test.


### Remarks
An **ELSEIF** can appear only within the context of an IF/ENDIF. If the previous [IF](IF.html)/ELSEIF comparison is met, the calculations before **ELSEIF** are processed; otherwise, if the **ELSEIF** condition is met, the calculations after **ELSEIF** (and before the next **ELSEIF** , ELSE or ENDIF) are processed. 

Conditioning indicator entries are not allowed.

### Example

```
If ACode = "A"
      ...
      ElseIf
        ACode = "B"
        ...
      ElseIf 
        AcRec = "D"
        ...
      Else
        ...
EndIf 
```

### See Also
[ELSE](ELSE.html)
[IF](IF.html) 

---
title: IF

Id: IF
TocParent: aerLrfOpCodesMain
TocOrder: 1140


---

IF processes a group of calculations if a [comparison expression evaluation](Expression_Operators_and_their_Precedence.html) is True. 

```

 **IF** 
 **Cond**  (Comparison Expression)
```

### Parts

**Cond** 

Required. The comparison expression is evaluated at the end of the execution of the group of commands between the [ENDIF](ENDIF.html), and [END](END.html). If the expression is true, the group of commands is executed again.


### Remarks
An **ENDIF** , or **END** is required to end the group of commands after the **IF** command. 

In Encore RPG, **IF** was expanded to include an **ELSEIF** .

### Example

```
If ACode = "A"
    ...
   ElseIf ACode = "B"
    ...
   ElseIf AcRec = "D"
    ...
   Else
    ...
 EndIf
```

### See Also
[ELSEIF](ELSEIF.html)

[END](END.html)

[ENDIF](ENDIF.html) 

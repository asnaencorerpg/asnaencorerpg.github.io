---
title: DOUNTIL

Id: DOUNTIL
TocParent: aerLrfOpCodesMain
TocOrder: 710


---

Begins a group of operations you want to process until a condition is True. The [ENDDO](ENDDO.html) command marks the end of the group. 

```

 **DOUNTIL** 
 **Cond**  (Comparison Expression)    
```

### Parts

**Cond** 

Required. The comparison expression is evaluated at the end of the execution of the group of commands between the **DOUNTIL** and the **ENDDO** . If the expression is False, the group of commands is executed again.


### Remarks
**DOUNTIL** first evaluates the complete condition. If the condition is False, the group of statements up to the **ENDDO** will be executed and control passes back to the **DOUNTIL** command again. If the condition is True, control passes to the next operations to be processed following the associated ENDDO command. 

### See Also
[DO](DO.html)
[DOWHILE](DOWHILE.html)
[ENDDO](ENDDO.html)
[ITERATE](ITERATE.html)
[LEAVE](LEAVE.html) 

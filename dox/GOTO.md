---
title: GOTO

Id: GOTO
TocParent: aerLrfOpCodesMain
TocOrder: 1110


---

Allows commands to be skipped by instructing the program to go to another command within the program. 

```

 **GOTO
Label** (label name)
```

### Parts

**Label** 

Required. Names the destination of a **GOTO** operation.


### Remarks
The **GOTO** operation allows calculation operations to be skipped by instructing the program to go to (or branch to) another calculation operation in the program. A [TAG](TAG.html) operation names the destination of a **GOTO** operation. 

**Use a GOTO operation to specify a branch:** 

- To a previous or a succeeding specification line.
- From a detail calculation line to another detail calculation line.
- From a total calculation line to another total calculation line.
- From a detail calculation line to a total calculation line.
- From a subroutine to a detail calculation line or to a total calculation line.

A **GOTO** operation outside a subroutine cannot specify a branch to a **TAG** or **ENDSR** operation within that subroutine. 

The **GOTO** command is **not** allowed within a **TRY/CATCH** block. 

### See Also
[ENDSR](ENDSR.html)
[Labels](Labels.html)
[TAG](TAG.html) 

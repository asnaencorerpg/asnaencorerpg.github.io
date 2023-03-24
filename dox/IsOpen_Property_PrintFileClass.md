---
title: PrintFile.IsOpen Property

Id: sOpen_Property_PrintFileClass
TocParent: aerLrfPrintFileProperties
TocOrder: 15


---

**IsOpen** gets a boolean value indicating whether the file is currently open for print operations. 

```

 *&lt;booleanVal&gt;*  = *printfile*  **.IsOpen** 
```

### Property Value
***&lt;booleanVal&gt;*** is of type *Boolean. 

**True** indicating the printfile is currently open for print operations. 

**False** indicating the printfile is **not** currently open for print operations. 

### Remarks
A file is considered "open" if it has been opened by the RPG program during initialization or by an **OPEN** operation, and has not subsequently been closed. 

If the file is conditioned by an external indicator and the external indicator was off at program initialization, the file is considered closed, and **IsOPEN** returns **False.** Refer to the [CLOSE](CLOSE.html) and [OPEN](OPEN.html) commands. 

**IsOpen** is equivalent to the [%OPEN](OPEN_Function.html) built-in function. 

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows Server 2012, Windows Server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

### See Also
[ASNA.VisualRPG.Runtime](aerLrfRuntimeNamespace.html)
[PrintFile Class](aerLrfPrintFileClass.html)
[PrintFile Members](aerLrfPrintFileMembers.html)
[DCLPRINTFILE](DCLPRINTFILE.html)
[CLOSE](CLOSE.html)
[OPEN](OPEN.html)
[%OPEN](OPEN_Function.html) 

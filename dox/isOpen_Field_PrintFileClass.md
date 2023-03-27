---
title: PrintFile.isOpen Field

Id: isOpen_Field_PrintFileClass
TocParent: aerLrfPrintFileFields
TocOrder: 4


---

Contains **True** when the file is currently open for print operations. 

```

 *printfile* 
 **.isOpen Type(*Boolean) Access(*Protected)** 
        
```

### Field Value
Boolean. Contains **True** or **False** indicating if the printfile is currently open ( **True** ) for print operations. 

### Remarks
A file is considered "open" if it has been opened by the RPG program during initialization or by an **OPEN** operation, and has not subsequently been closed. 

If the file is conditioned by an external indicator and the external indicator was off at program initialization, the file is considered closed, and **isOPEN** returns **False** . 

**isOpen** is equivalent to the [%OPEN](OPEN_Function.html) built-in function. 

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

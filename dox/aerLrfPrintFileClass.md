---
title: PrintFile Class

Id: aerLrfPrintFileClass
TocParent: aerLrfRuntimeNamespace
TocOrder: 8


---

The PrintFile class contains all the information for printing in a program. 

For alist of all members of this type, see [PrintFile Members](aerLrfPrintFileMembers.html). 

[ASNA.VisualRPG.Runtime](aerLrfRuntimeNamespace.html) <br /> ASNA.VisualRPG.Runtime. **PrintFile** 

```
&lt;Serializable&gt;
 **Syntax** 
```

### Thread Safety
This type is safe for multithreaded operations.

### Remarks
A PrintFile class simply defines a DataGate printfile for printing at run-time. At compile time, the description of the file is read in with its record format. The file name and each record format name must be unique. 

Print Files are always opened for sequential output operation. 

See [DCLPRINTFILE](DCLPRINTFILE.html) for more information.

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows server 2012, Windows server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

### See Also
[ASNA.VisualRPG.Runtime](aerLrfRuntimeNamespace.html)
[PrintFile Members](aerLrfPrintFileMembers.html)
[DCLPRINTFILE](DCLPRINTFILE.html) 

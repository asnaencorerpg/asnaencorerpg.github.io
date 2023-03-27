---
title: PrintFile.DclPrintFileName Field

Id: DclPrintFileName_Field
TocParent: aerLrfPrintFileFields
TocOrder: 1


---

**DclPrintFileName** contains the print file *Name* as declared for the print file (see [DCLPRINTFILE](DCLPRINTFILE.html)). 

```

 *printfile* . **DclPrintFileName Type(*String)** 
```

### Field Value
String. The *Name* of the print file declared by **DCLPRINTFILE** .

### Remarks
**DclPrintFileName** can contain, as defined by **DCLPRINTFILE** , either: 

- The name of the variable already defined.
- A string literal, which defines an *OBJECT variable of a particular type. The string literal must represent:
- a valid program id registered on your system at compile time.
- a valid class id registered on your system at compile time.
- a valid interface name registered on your system at compile time.

- A name of the form **Library.Object** , where Library is the name of one of the libraries selected in the new object libraries dialog, and Object is valid object name within that library.

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows server 2012, Windows server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

### See Also
[ASNA.VisualRPG.Runtime](ecrLrfRuntimeNamespace.html)

[PrintFile Class](ecrLrfPrintFileClass.html)

[PrintFile Members](ecrLrfPrintFileMembers.html)

[DCLPRINTFILE](DCLPRINTFILE.html) 

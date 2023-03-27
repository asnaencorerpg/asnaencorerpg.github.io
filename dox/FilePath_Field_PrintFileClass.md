---
title: PrintFile.FilePath Field

Id: FilePath_Field_PrintFileClass
TocParent: aerLrfPrintFileFields
TocOrder: 2


---

**FilePath** contains a string that specifies the path of the file. 

```

 *printfile* . **FilePath Type(*String)** 
```

### Field Value
String. The path of the print file to use when opened at file at run-time. 

### Remarks
**FilePath** must be set prior to opening a file (see [OPEN](OPEN.html) command). 

If **FilePath** is not set, the Library and File of the *File* parameter specified in the [DCLPRINTFILE](DCLPRINTFILE.html) command is used. 

Setting the **FilePath** prior to opening a file is equivalent to the System i process called **override database file** . 

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows server 2012, Windows server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

### See Also
[ASNA.VisualRPG.Runtime](ecrLrfRuntimeNamespace.html)

[PrintFile Class](ecrLrfPrintFileClass.html)

[PrintFile Members](ecrLrfPrintFileMembers.html)

[DCLPRINTFILE](DCLPRINTFILE.html)

[OPEN](OPEN.html) 

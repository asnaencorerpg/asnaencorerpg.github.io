---
title: PrintFile.IsFormatID Field

Id: IsFormatID_Field_PrintFileClass
TocParent: aerLrfPrintFileFields
TocOrder: 3


---

**IsFormatID** contains **True** if the opened (run-time) file's format is equal to the declared (compile-time) file's format. 

```

 *printfile* 
 **.IsformatID Type(*Boolean)** 
```

### Field Value
Boolean. **True** if the format ID of the file specified in the **DclPrintFile** 's ** *FileDesc* ** parameter is the same as the file opened at run-time. 

### Remarks
**IsFormatID** indicates if the format ID of the file at run-time compares to the format ID of the file at compile-time. 

When the ** *ChkFmtID* ** parameter specified in the [DCLPRINTFILE](DCLPRINTFILE.html) command is set to * **Yes** or * **Same** , **IsFormatID** contains **True** if the format ID of the file specified in the **DclPrintfile** 's ** *FileDesc* ** parameter is the same as the file opened at run-time. 

The Encore RPG compiler stores the format ID of each file in the assembly when a program is compiled. At run-time, ECR can then compare the stored format ID with the format ID of the currently-opened file. 

At run-time, Encore RPG compares the format ID that was stored during the compilation with the current format ID. The comparing of format ID's can be especially useful when checking if new fields have been added to a file used by a program that has been compiled months ago. 

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows server 2012, Windows server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

### See Also
[ASNA.VisualRPG.Runtime](aerLrfRuntimeNamespace.html)

[PrintFile Class](aerLrfPrintFileClass.html)

[PrintFile Members](aerLrfPrintFileMembers.html)

[DCLPRINTFILE](DCLPRINTFILE.html) 

---
title: PrintFile.FormName Property

Id: FormName_Property
TocParent: aerLrfPrintFileProperties
TocOrder: 5


---

**FormName** gets or sets the name of the customized page size to use. 

```

 *printfile* . **FormName**  = *<stringVal>* 
```

### Property Value
*<stringVal>* is of type *String containing the name of the customized page size to use (see [PaperSize](PaperSize_Property.html)). 

### Remarks
Must be set prior to opening the printer file (see [OPEN](OPEN.html) command).

If **FormName** is not set, the form name for the print file will be used. 

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows server 2012, Windows server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

### See Also
[ASNA.VisualRPG.Runtime](aerLrfRuntimeNamespace.html)
[PrintFile Class](aerLrfPrintFileClass.html)
[PrintFile Members](aerLrfPrintFileMembers.html)
[PaperSize Property](PaperSize_Property.html)
[OPEN](OPEN.html)
[DCLPRINTFILE](DCLPRINTFILE.html) 

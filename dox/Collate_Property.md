---
title: PrintFile.Collate Property

Id: Collate_Property
TocParent: aerLrfPrintFileProperties
TocOrder: 0


---

**Collate** gets or sets whether collation will be used when printing multiple copies. 

```

 *printfile* 
 **.Collate** = *<booleanVal>* 
```

### Settings
***<booleanVal>*** 

**True** indicates the printfile is to be collated. 

**False** indicates if the printfile is **not** to be collated. 

### Remarks
Must be set prior to opening the printer file (see [OPEN](OPEN.html) command). 

Setting this property to **True** will allow multiple copies to be collated. However, this property is applicable only when printing multiple copies, or when the [Copies](Copies_Property.html) property is >1. 

If **Collate** is not set, the collate setting specified for the print file will be used. (If *DEFAULT is specified for the print file, then the collate setting specified for the printer will be used). 

The collation is handled by the printer, rather than software. If the printer itself does not support collate, then no collation will occur. 

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows server 2012, Windows server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

### See Also
[ASNA.VisualRPG.Runtime](aerLrfRuntimeNamespace.html)
[PrintFile Class](aerLrfPrintFileClass.html)
[PrintFile Members](aerLrfPrintFileMembers.html)
[DCLPRINTFILE](DCLPRINTFILE.html)
[Copies Property](Copies_Property.html)
[OPEN](OPEN.html) 

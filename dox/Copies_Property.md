---
title: PrintFile.Copies Property

Id: Copies_Property
TocParent: aerLrfPrintFileProperties
TocOrder: 1


---

**Copies** gets or sets the number of copies to print. 

```

 *printfile* . **Copies**  = *&lt;integerVal&gt;* 
```

### Settings
***&lt;integerVal&gt;*** containing the number of copies to print. 

### Remarks
Must be set prior to opening the printer file, or prior to **FEOD** with reset (see [OPEN](OPEN.html) and [FEOD](FEOD.html) command). 

If **Copies** is not set, the number of copies specified for the print file will be used. If *DEFAULT is specified for the print file, then the default number of copies specified for the printer will be used. 

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows server 2012, Windows server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

### See Also
[ASNA.VisualRPG.Runtime](aerLrfRuntimeNamespace.html)
[PrintFile Class](aerLrfPrintFileClass.html)
[PrintFile Members](aerLrfPrintFileMembers.html)
[OPEN](OPEN.html)
[FEOD](FEOD.html)
[DCLPRINTFILE](DCLPRINTFILE.html) 

---
title: PrintFile.ReportName Property

Id: ReportName_Property
TocParent: aerLrfPrintFileProperties
TocOrder: 22


---

**ReportName** gets or sets the name of the report as seen on the printer spool. 

```

 *printfile* 
 **.ReportName = *&lt;stringVal&gt;* ** 
        
```

### Property Value
***&lt;stringVal&gt;*** is of type *String and contains the name of the report. 

### Remarks
If **ReportName** is not assigned, the default name is the name given when the print file was declared. This is the name of the print file seen on the printer spool. 

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows Server 2012, Windows Server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

### See Also
[ASNA.VisualRPG.Runtime](aerLrfRuntimeNamespace.html)
[PrintFile Class](aerLrfPrintFileClass.html)
[PrintFile Members](aerLrfPrintFileMembers.html)
[DCLPRINTFILE](DCLPRINTFILE.html) 

---
title: PrintFile.TTOPTION Property

Id: Ttoption_Property
TocParent: aerLrfPrintFileProperties
TocOrder: 24


---

**TTOption** gets or sets how Microsoft ***TueType*** fonts are to be printed. 

```

 *printfile* . **TTOption= ASNA.DataGate.Common.PrintTrueType** . *<value>* 
```

### Property Value
***<value>*** is of type . 

- *FILE indicates that the True Type option specified for the print file will be used. (If *DEFAULT is specified for the print file, then the True Type option specified for the printer will be used).
- BITMAP indicates that True Type fonts will print as graphics.
- DOWNLOAD indicates that True Type fonts will be downloaded as soft fonts.
- SUBDEVFONT indicates that device fonts will be substituted for True Type fonts.

### See Also
[ASNA.VisualRPG.Runtime](aerLrfRuntimeNamespace.html)
[PrintFile Class](aerLrfPrintFileClass.html)
[PrintFile Members](aerLrfPrintFileMembers.html)
[DCLPRINTFILE](DCLPRINTFILE.html) <br /> 

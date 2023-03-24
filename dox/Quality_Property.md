---
title: PrintFile.Quality Property

Id: Quality_Property
TocParent: aerLrfPrintFileProperties
TocOrder: 21


---

**Quality** gets or sets the print quality. 

```

 *printfile* . **Quality = System.Drawing.Printing.PrinterResolutionKind.** *&lt;value&gt;* 
```

### Property Value
***&lt;value&gt;*** is of type enum and contains the enumeration value for the print quality. 

Please note that not all of the possible values for this enumeration may be valid for your printer. Each printer has a limited set of acceptable values. It is up to the programmer to select the value adequate to the actual printer used to render the output of the print file. 

### Remarks
**Quality** must be set prior to opening the printer file (see [OPEN](OPEN.html) command). 

Set the **Quality** property to specify the print quality. *FILE indicates that the print quality specified for the print file will be used. If *DEFAULT is specified for the print file, then the default print quality specified for the printer will be used. 

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows Server 2012, Windows Server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

#### See Also
<p> [ASNA.VisualRPG.Runtime](aerLrfRuntimeNamespace.html)
[PrintFile Class](aerLrfPrintFileClass.html)
[PrintFile Members](aerLrfPrintFileMembers.html)
[OPEN](OPEN.html)
[DCLPRINTFILE](DCLPRINTFILE.html) <br /> 

---
title: PrintFile.PaperSize Property

Id: PaperSize_Property
TocParent: aerLrfPrintFileProperties
TocOrder: 12


---

**PaperSize** gets or sets the paper size to be used when printing. 

```

 *printfile* . **PaperSize = System.Drawing.Printing.PaperKind.** *&lt;value&gt;* 
```

### Property Value
***&lt;value&gt;*** is of type enum and is the enumeration value indicating the paper size. 

Please note that not all of the possible values for this enumeration may be valid for your printer. Each printer has a limited set of acceptable values. It is up to the programmer to select the value adequate to the actual printer used to render the output of the print file. 

### Remarks
Must be set prior to opening the printer file (see [OPEN](OPEN.html) command).

IF **PaperSize** is not set, the paper size specified for in the print file will be used. (If *DEFAULT is specified for the print file, then the default paper size, based on the [orientation](Orientation_Property.html) of the printer, will be used.) 

- To get the measurement in millimeters, divide by 100.
- To get the measurement in centimeters, divide by 1,000.
- To get the measurement in inches, divide by 2,540

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows Server 2012, Windows Server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

#### See Also
[ASNA.VisualRPG.Runtime](aerLrfRuntimeNamespace.html)
[PrintFile Class](aerLrfPrintFileClass.html)
[PrintFile Members](aerLrfPrintFileMembers.html)
[OPEN](OPEN.html)
[Orientation Property](Orientation_Property.html)
[DCLPRINTFILE](DCLPRINTFILE.html) <br /> 

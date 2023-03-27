---
title: PrintFile.PaperSource Property

Id: PaperSource_Property
TocParent: aerLrfPrintFileProperties
TocOrder: 13


---

**PaperSource** gets or sets the printer tray with will be used when printing. 

```

 *printfile* . **PaperSource = System.Drawing.Printing.PaperSourceKind.** *<value>* 
```

### Property Value
***<value>*** is of type enum and is the enumeration value indicating the source of the paper tray. 

Please note that not all of the possible values for this enumeration may be valid for your printer. Each printer has a limited set of acceptable values. It is up to the programmer to select the value adequate to the actual printer used to render the output of the print file. 

### Remarks
Must be set prior to opening the printer file (see [OPEN](OPEN.html) command).

If **PaperSource** is not set, the paper source specified for the print file will be used. (If *DEFAULT is specified for the print file, then the default orientation of the printer will be used.) 

Printer manufacturers can implement their own paper source code values which are different from the standard PaperSource values. Common printer tray options include upper tray, lower tray, middle tray, manual feed, envelopes, etc. Please note that each printer will contain the paper tray options that are available for that printer. 

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

[DCLPRINTFILE](DCLPRINTFILE.html) <br /> 

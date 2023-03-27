---
title: PrintFile.Duplex Property

Id: Duplex_Property
TocParent: aerLrfPrintFileProperties
TocOrder: 3


---

**Duplex** gets or sets how duplex (double-sided) printing will be used. 

```

 *printfile* . **Duplex**  = System.Drawing.Printing.Duplex *.<setting>* 
```

### Property Value
***<setting>*** is of ** type 

Also note that not all of the possible values for this enumeration may be valid for your printer. Each printer has a limited set of acceptable values. It is up to the programmer to select the value adequate to the actual printer used to render the output of the print file. 

### Remarks
Must be set prior to opening the printer file (see [OPEN](OPEN.html) command). 

If **Duplex** is not set, the duplex type specified for the print file will be used. (If *DEFAULT is specified for the print file, then the duplex option specified for the printer will be used). 

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows server 2012, Windows server 2012 R2, Windows Server 2016, Windows XP Professional SP2, Windows Vista Business Edition, Windows 7, Windows 8, Windows 10. 

### See Also
[ASNA.VisualRPG.Runtime](ecrLrfRuntimeNamespace.html)

[PrintFile Class](ecrLrfPrintFileClass.html)

[PrintFile Members](ecrLrfPrintFileMembers.html)

[OPEN](OPEN.html)

[DCLPRINTFILE](DCLPRINTFILE.html) <br /> 

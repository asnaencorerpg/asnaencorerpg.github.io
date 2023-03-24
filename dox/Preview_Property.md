---
title: PrintFile.Preview Property

Id: Preview_Property
TocParent: aerLrfPrintFileProperties
TocOrder: 15


---

**Preview** gets or sets whether the print preview dialog is to be displayed before printing. 

```

 *printfile* . **Preview = ASNA.DataGate.Common.AccessMode.** < *value>* 
```

### Property Value
*<value>* is of type [ASNA.DataGate.Common.AccessMode](AdgCommon_AccessMode.html) and is the enumeration value for the property. 

### Remarks
Must be set prior to opening the printer file (see [OPEN](OPEN.html) command).

**Preview** allows for easy previewing of printer file output. Setting this property to "PrintPreview" prior to opening the printer file will result in the print driver commands being saved to a temporary file on the client machine, and when the print file is closed, or the [FEOD](FEOD.html) command is issued, a preview of the printed output is displayed (nothing is yet sent to the printer). While previewing, the user has the option to then send the output to the target printer. 

IF **Preview** is not set, the preview setting specified for in the print file will be used. 

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows Server 2012, Windows Server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

#### See Also
[ASNA.VisualRPG.Runtime](aerLrfRuntimeNamespace.html)
[PrintFile Class](aerLrfPrintFileClass.html)
[PrintFile Members](aerLrfPrintFileMembers.html)
[OPEN](OPEN.html)
[FEOD](FEOD.html)
[DCLPRINTFILE](DCLPRINTFILE.html)
[ASNA.DataGate.Common.AccessMode Enumeration](AdgCommon_AccessMode.html) 

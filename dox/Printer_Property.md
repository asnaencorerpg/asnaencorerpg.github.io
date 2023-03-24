---
title: PrintFile.Printer Property

Id: Printer_Property
TocParent: aerLrfPrintFileProperties
TocOrder: 18


---

**Printer** gets or sets the full path name of the printer to be used. 

```

 *printfile* . **Printer =** *&lt;stringVal&gt;* 
```

### Property Value
***&lt;stringVal&gt;*** is of type *String and contains the full path name of the printer to be used. 

### Remarks
**Printer** must be set prior to opening the printer file (see [OPEN](OPEN.html) command). 

To specify a **Printer** , enter the complete path and name of the printer. For example, if the Printer is on a network, you must specify the network, then the Printer name. For example, " **\\Network\HP LaserJet 5M** ". 

If you are unsure about the correct printer name used by the operating system, simply select *Print* in Word or other Microsoft product and the printer names displayed will be in the correct format. 

If **Printer** is not set, the default printer for the operating system will be used. 

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows Server 2012, Windows Server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

#### See Also
[ASNA.VisualRPG.Runtime](aerLrfRuntimeNamespace.html)
[PrintFile Class](aerLrfPrintFileClass.html)
[PrintFile Members](aerLrfPrintFileMembers.html)
[OPEN](OPEN.html)
[DCLPRINTFILE](DCLPRINTFILE.html) 

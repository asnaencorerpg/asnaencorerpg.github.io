---
title: PrintFile.PrintSetup Property

Id: PrintSetup_Property
TocParent: aerLrfPrintFileProperties
TocOrder: 19


---

**PrintSetup** gets or sets whether the print setup dialog is to display before printing. 

```

 *printfile* . **PrintSetup =** *&lt;booleanVal&gt;* 
```

### Property Value
***&lt;booleanVal&gt;*** is of type *Boolean. 

**True** will display the setup dialog. 

**False** will not display the setup dialog. 

### Remarks
**PrintSetup** must be set prior to opening the printer file (see [OPEN](OPEN.html) command). 

Setting **PrintSetup** property to **True** prior to opening the printer file will result in the print setup dialog being displayed when the print file is opened. This allows the user to select print settings prior to printing. 

<p> IF **PrintSetup** is set to **False** , the print setup dialog will not be displayed. If **PrintSetup** is not set, the print setup setting specified for the file will be used. 

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

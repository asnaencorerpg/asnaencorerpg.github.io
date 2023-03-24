---
title: PrintFile.Orientation Property

Id: Orientation_Property
TocParent: aerLrfPrintFileProperties
TocOrder: 10


---

**Orientation** gets or sets the print orientation. 

```

 *printfile* . **Orientation = ASNA.DataGate.Common.PaperOrientation** *.&lt;value&gt;* 
```

### Property Value
*&lt;value&gt;* is of type and is the enumeration value indicating the print orientation. 

### Remarks
**Orientation** must be set prior to opening the printer file (see [OPEN](OPEN.html) command). 

The page orientation can be set to either Portrait or Landscape. If **Orientation** is not set, the orientation specified for the print file will be used. (If *DEFAULT is specified for the print file, then the default orientation of the printer will be used.) 

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

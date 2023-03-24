---
title: PrintFile.PageWidth Property

Id: PageWidth_Property
TocParent: aerLrfPrintFileProperties
TocOrder: 210

---

**OBSOLETE** : This property is marked obsolete and is referenced only for backward compatibility. This has been replaced with [PrintableWidth](PrintableWidth_Property.html) property. 

Gets the width of the printable area on the paper, in Print Units, based on the page orientation selected. 

```
*Integer4 = *printfile* . **PageWidth** 
```

### Property Value
Integer. The width of the printable area on the paper, in Print Units, based on the page orientation selected. 

### Remarks
Must be set prior to opening the printer file (see [OPEN](OPEN.html) command). 

If **PageWidth** is not set, the page width specified for the print file will be used. (If *DEFAULT is specified for the print file, then the default page width, based upon the [orientation](Orientation_Property.html) of the paper in the printer will be used. 

Print Units are measured in 1/100<sup>th</sup> of a millimeter. 

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
[Orientation Property](Orientation_Property.html)
[OPEN](OPEN.html)
[DCLPRINTFILE](DCLPRINTFILE.html) 

---
title: PrintFile.PageLength Property

Id: PageLength_Property
TocParent: aerLrfPrintFileProperties
TocOrder: 200

---

**OBSOLETE:** This property is marked obsolete and is referenced only for backward compatibility. This has been replaced with [PrintableLength](PrintableLength_Property.html) property. 

Gets the length of the printable area on the paper, in Print Units, based on the page orientation selected. 

```
*Integer4 = *printfile* . **PageLength** 
```

### Property Value
Integer4. The length of the printable area on the paper, in Print Units, based on the page orientation selected. 

### Remarks
Must be set prior to opening the printer file (see [OPEN](OPEN.html) command). 

If **PageLength** is not set, the page length specified for the print file will be used. (If *DEFAULT is specified for the print file, then the default page length, based upon the [Orientation](Orientation_Property.html) of the paper in the printer will be used. 

Print Units are measured in 1/100<sup>th</sup> of a millimeter. 

- To get the measurement in millimeters, divide by 100.
- To get the measurement in centimeters, divide by 1,000.
- To get the measurement in inches, divide by 2,540

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows Server 2012, Windows Server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

#### See Also
[ASNA.VisualRPG.Runtime](ecrLrfRuntimeNamespace.html)

[PrintFile Class](ecrLrfPrintFileClass.html)

[PrintFile Members](ecrLrfPrintFileMembers.html)

[Orientation Property](Orientation_Property.html)

[OPEN](OPEN.html)

[DCLPRINTFILE](DCLPRINTFILE.html) 

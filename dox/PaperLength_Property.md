---
title: PrintFile.PaperLength Property

Id: PaperLength_Property
TocParent: aerLrfPrintFileProperties
TocOrder: 11


---

**PaperLength** gets or sets the physical length of the page. 

```

 *printfile* . **PaperLength =** *&lt;integerVal&gt;* 
```

### Property Value
***&lt;integerVal&gt;*** of type *Integer4 and contains the physical length of the page in the printer. This is valid only with a continuous-form printer. 

### Remarks
Must be set prior to opening the printer file (see [OPEN](OPEN.html) command). 

If **PaperLength** is not set, the paper length specified for the print file will be used. (If *DEFAULT is specified for the print file, then the default paper length, based upon the [orientation](Orientation_Property.html) of the paper in the printer will be used. These values are in tenths of a millimeter. 

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

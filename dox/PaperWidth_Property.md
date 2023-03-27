---
title: PrintFile.PaperWidth Property

Id: PaperWidth_Property
TocParent: aerLrfPrintFileProperties
TocOrder: 14


---

**PaperWidth** gets or sets the physical width of the paper. 
<pre class="prettyprint">
 *printfile* . **PaperWidth =** *<integerVal>* </pre>

### Property Value
***<integerVal>*** is of type *Integer4 and contains the physical width of the paper. Valid only with a continuous-form printer. 

### Remarks
Must be set prior to opening the printer file (see [OPEN](OPEN.html) command).

If **PaperWidth** is not set, the paper width Print Units specified for the print file will be used. (If *DEFAULT is specified for the print file, then the default paper width, based upon the [Orientation](Orientation_Property.html) of the paper in the printer will be used. 

Print Units are measured in 1/100<sup>th</sup> of a millimeter. 

- To get the measurement in millimeters, divide by 100.
- To get the measurement in centimeters, divide by 1,000.
- To get the measurement in inches, divide by 2,540.

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

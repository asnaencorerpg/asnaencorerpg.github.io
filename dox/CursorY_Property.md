---
title: PrintFile.CursorY Property

Id: CursorY_Property
TocParent: aerLrfPrintFileProperties
TocOrder: 2


---

**CursorY** gets the position, in Print Units, that the printer is from the top of the page. 

```

 *<integerVal>*  = *printfile* . **CursorY** 
```

### Property Value
***<integerVal>*** is of type *Integer4 and contains the position, in Print Units, that the printer is from the top of the page. 

Print Units are measured in 1/100<span style="VERTICAL-ALIGN: super">th</span> of a millimeter. 

- To get the measurement in millimeters, divide by 100.
- To get the measurement in centimeters, divide by 1,000.
- To get the measurement in inches, divide by 2,540.

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows server 2012, Windows server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

### See Also
[ASNA.VisualRPG.Runtime](aerLrfRuntimeNamespace.html)
[PrintFile Class](aerLrfPrintFileClass.html)
[PrintFile Members](aerLrfPrintFileMembers.html)
[DCLPRINTFILE](DCLPRINTFILE.html) 

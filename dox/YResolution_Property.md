---
title: PrintFile.YResolution Property

Id: YResolution_Property
TocParent: aerLrfPrintFileProperties
TocOrder: 26


---

**YResolution** gets or sets the y-axis resolution in dots per inch, in which graphics will be printed. 

```

 printfile.YResolution = <integerVal>
```

### Property Value
\<*integerVal*\> is of type *Integer4 and contains the value that defines the y-axis resolution in dots per inch, in which graphics will be printed. 

### Remarks
**YResolution** must be set prior to opening the print file (see [OPEN](OPEN.html) command). 

Setting **YResolution** specifies the Y-axis resolution, in dots per inch. If no **YResolution** is specified, then the y-resolution specified for the printer will be used. 

Printers support one or more horizontal and vertical resolutions for faster graphics output. A resolution is an integer value specified in dots-per-inch (dpi), which indicates the number of distinct dots that the print head or inkjet can apply along the x- or the y-axis. 

Typically, the x-y resolutions will be the same, such as300 x 300, or 600 x 600, etc. Since the x-y resolutions are the same, you only need to specify the y-resolution. 

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA.VisualRPG.Runtime(in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows Server 2012, Windows Server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

### See Also
[ASNA.VisualRPG.Runtime](aerLrfRuntimeNamespace.html)

[PrintFile Class](aerLrfPrintFileClass.html)

[PrintFile Members](aerLrfPrintFileMembers.html)

[OPEN](OPEN.html)

[DCLPRINTFILE](DCLPRINTFILE.html) 

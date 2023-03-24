---
title: PrintFile.ProcessMacro Property

Id: ProcessMacro_Property
TocParent: aerLrfPrintFileProperties
TocOrder: 20


---

**ProcessMacro** gets or sets a boolean value indicating if DataGate print engine should search for page numbering "macros" and replaced them with appropriate data before sending the output to the printer. 

```

 *printfile* . **ProcessMacros =** *&lt;booleanVal&gt;* 
```

### Property Value
***&lt;booleanVal&gt;*** is of type *Boolean. 

**True** to search and replace page number information in the print file before printing. 

**False** to **not** search and replace page number information in the print file before printing. 

### Remarks
**ProcessMacro** must be set prior to opening the printer file (see [OPEN](OPEN.html) command). 

Setting **ProcessMacro** property **True** will cause the DataGate print engine to search for page numbering "macros" and replace them with the appropriate data as indicated below. 

The following macros are currently available: 

- &amp;# - This is replaced with the current page number.
- &amp;$ - This is replaced with the page count.

Macros may only be described in a Print file label control. Only one macro per Label control is allowed (e.g. "Page &amp;# of &amp;$" is not valid). You may, however, describe the same macro more than once per format and/or per print file. 

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows 2000 Professional SP4, Windows 2000 Server SP4, Windows Server 2003, Windows XP Professional SP2, Windows Vista Business Edition 

#### See Also
[ASNA.VisualRPG.Runtime](aerLrfRuntimeNamespace.html)
[PrintFile Class](aerLrfPrintFileClass.html)
[PrintFile Members](aerLrfPrintFileMembers.html)
[OPEN](OPEN.html)
[DCLPRINTFILE](DCLPRINTFILE.html) 

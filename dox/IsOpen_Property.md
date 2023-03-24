---
title: Database.IsOpen Property

Id: IsOpen_Property
TocParent: aerLrfDatabasePropertiesMain
TocOrder: 4


---

**IsOpen** gets a boolean value indicating if the file is currently open for I/O operations. 

```

 *&lt;booleanVal&gt;* 
 **=** 
 *database* 
 **.IsOpen** 
        
```

### Returns
** *&lt;booleanVal&gt;* ** . 

**True** indicates the file is currently open for I/O operations. 

**False** indicates the file is currently **not** open for I/O operations. 

### Remarks
Refer to the [CLOSE](CLOSE.html) and [OPEN](OPEN.html) commands. 

**IsOpen** is equivalent to the [%OPEN](OPEN_Function.html) built-in function. 

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows Server 2012, Windows Server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

### See Also
[ASNA.VisualRPG.Runtime](aerLrfRuntimeNamespace.html)
[Database Class](Date_Formats.html)
[Database Class Members](aerLrfDatabasePropertiesMain.html)
[Database Class Properties](aerLrfDatabasePropertiesMain.html)
[DCLDISKFILE](DCLDISKFILE.html)
[CLOSE](CLOSE.html)
[OPEN](OPEN.html)
[%OPEN](OPEN_Function.html) 

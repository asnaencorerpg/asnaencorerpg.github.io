---
title: DBFile.RecNum Property

Id: RecNum_Property
TocParent: aerLrfDBFilePropertiesMain
TocOrder: 8


---

**RecNum** gets the current RRN for the last input operation to a file. 

```

 *<integerVal>* 
 **=** 
 *dbfile* . **RecNum**   
```

### Property Value
***<integerVal>*** is of type *Integer8 and contains the current RRN for the last input operation to a file. 

### Remarks
The Relative Record Number ( RRN ) is relative to 1.

RRN is not supported by Microsoft's SQL Server database engine.

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows Server 2012, Windows Server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

### See Also
[ASNA.VisualRPG.Runtime](aerLrfRuntimeNamespace.html)

[Database Class](Date_Formats.html)

[Database Class Members](aerLrfDatabasePropertiesMain.html)

[DCLDISKFILE](DCLDISKFILE.html)

[OPEN](OPEN.html)

[RecCount Property](RecCount_Property.html) 

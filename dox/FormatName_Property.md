---
title: DBFile.FormatName Property

Id: FormatName_Property
TocParent: aerLrfDBFilePropertiesMain
TocOrder: 0


---

**FormatName** gets the name of the record format last read or written. 

```

 *<stringVal>*  = *dbfile*  **.**  **FormatName**   
```

### Property Value
***<stringVal>*** of type *String containing the name of the record format last read or written. 

### Remarks
The System i database engine supports a logical file type called " **multiformat** ". This file is based upon two or more physical files. The contents of the **FormatName** property are useful when reading from a multiformat file. When reading sequentially through a multiformat file, you can determine the format last read from the content of **FormatName** . 

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows server 2012, Windows server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

### See Also
[ASNA.VisualRPG.Runtime](ecrLrfRuntimeNamespace.html)

[DBFile Class](ecrLrfDBFileClass.html)

[DBFile Members](ecrLrfDBFileMembers.html) 

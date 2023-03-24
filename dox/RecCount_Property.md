---
title: DBFile.RecCount Property

Id: RecCount_Property
TocParent: aerLrfDBFilePropertiesMain
TocOrder: 7


---

The **RecCount** property gets the current number of non-deleted records in the file. 

```

 *<integerVal>*  = *dbfile* . **RecCount**  
```

### Property Value
*<integerVal>* is of type *Integer8 and contains the current number of non-deleted records in the file. 

### Remarks
The file must first be [Opened](OPEN.html) before the record count is available. 

If the file is a logical file, the record count returned is that of the base physical file. 

The record count returned can differ for logical files depending upon the database engine. 

- **DataGate Windows** : The count is active records in the base file.
- **DB2/400** : The count is the active records in the logical view. If the file is opened with **QrySelect** , the record count is the active records of the queried file, not the records returned for the query.
- **SQL Server** : The count is the active records in the logical view. If the file is opened with **QrySelect** , the record count is the active records of the queried file, not the records returned for the query.

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
[RecNum Property](RecNum_Property.html) 

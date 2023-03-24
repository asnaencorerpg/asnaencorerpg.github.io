---
title: Database.CopyFileToDb Method

Id: CopyFileToDb_Method
TocParent: aerLrfDatabaseMethods
TocOrder: 20


---

**CopyFileToDb** copies a physical file from the current database to another database. 

```

 *database* .CopyFileToDb (FilePath, ToDb, ToDirectory, CopyData)
```

### Parameters

**FilePath** 

Required.  A string containing the path to the database file
                as "directory/fileName".


**ToDb** 

Required.  A Database object representing the database where the logical file
                will be copied.


**ToDirectory** 

Required.  A string containing the destination
                directory.


**CopyData** 

Required.  A boolean indicating whether the
                physical file data is also to be copied.


### Remarks
Use the **CopyFileToDb** method to copy a physical file with all its members and optionally all its data from the current database to another database. 

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows server 2012, Windows server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

### See Also
[ASNA.VisualRPG.Runtime](aerLrfRuntimeNamespace.html)
[Database Class](aerLrfDatabaseClass.html)
[Database Class Members](aerLrfDatabaseMembers.html)
[Database Class Properties](aerLrfDatabasePropertiesMain.html)
[Database Class Methods](aerLrfDatabaseMethods.html)
[DCLDB](DCLDB.html) 

---
title: Database.CopyLogicalFileToDb Method

Id: CopyLogicalFileToDb_Method
TocParent: aerLrfDatabaseMethods
TocOrder: 30


---

**CopyLogicalFileToDb** copies a logical file and its base physical files from the current database to another database. 

```

 *database* .CopyLogicalFileToDb (FilePath, ToDb, ToDirectory, ReplaceBaseFiles, CopyData)
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


**ReplaceBaseFiles** 

Required.  A boolean indicating whether to replace a
                physical file if it already exists in the destination
                database.


**CopyData** 

Required.  A boolean indicating whether the
                physical file data is also to be copied.


### Remarks
Use the **CopyLogicalFileToDb** method to copy a logical file with all its base physical files from the current database to another. When the **ReplaceBaseFiles** parameter is *TRUE the base physical files will be replaced if they already exist in the destination database. 

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows server 2012, Windows server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

### See Also
[ASNA.VisualRPG.Runtime](ecrLrfRuntimeNamespace.html)

[Database Class](ecrLrfDatabaseClass.html)

[Database Class Members](ecrLrfDatabaseMembers.html)

[Database Class Properties](ecrLrfDatabasePropertiesMain.html)

[Database Class Methods](ecrLrfDatabaseMethods.html)

[DCLDB](DCLDB.html) 

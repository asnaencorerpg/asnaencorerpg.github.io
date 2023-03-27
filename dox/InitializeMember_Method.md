---
title: Database.InitializeMember Method

Id: InitializeMember_Method
TocParent: aerLrfDatabaseMethods
TocOrder: 90


---

**InitializeMember** initializes a file member with the specified number of deleted records. 

```

 *database* .InitializeMember (FilePath, MemberName, RecordCount)
```

### Parameters

**FilePath** 

Required.  A string containing the path to the database file
                as "directory/fileName".


**MemberName** 

Required.  A string containing the member name to
                initialize.


**RecordCount** 

Required.  An integer quantity representing the number of deleted
                records to add to the member.


### Remarks
Use the **InitializeMember** method to programmatically initialize a database file member with zero or more deleted records. 

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows server 2012, Windows server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. <br /> 

### See Also
[ASNA.VisualRPG.Runtime](ecrLrfRuntimeNamespace.html)

[Database Class](Date_Formats.html)

[Database Class Members](ecrLrfDatabasePropertiesMain.html)

[Database Class Properties](ecrLrfDatabasePropertiesMain.html)

[Database Class Methods](ecrLrfDatabaseMethods.html)

[DCLDB](DCLDB.html) 

---
title: Database.RenameMember Method

Id: RenameMember_Method
TocParent: aerLrfDatabaseMethods
TocOrder: 13


---

**RenameMember** changes the name of a member in a database file. 

```

 *database* .RenameMember (FilePath, MemberName, NewName)
```

### Parameters

**FilePath** 

Required.  A string containing the path to the database file
                as "directory/fileName".


**MemberName** 

Required.  A string containing the current member name.


**NewName** 

Required.  A string containing the new member name.


### Remarks
Use the **RenameMember** method to change programmatically the name of a database file member.

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows Server 2012, Windows Server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

### See Also
[ASNA.VisualRPG.Runtime](ecrLrfRuntimeNamespace.html)

[Database Class](Date_Formats.html)

[Database Class Members](ecrLrfDatabasePropertiesMain.html)

[Database Class Properties](ecrLrfDatabasePropertiesMain.html)

[Database Class Methods](ecrLrfDatabaseMethods.html)

[DCLDB](DCLDB.html) 

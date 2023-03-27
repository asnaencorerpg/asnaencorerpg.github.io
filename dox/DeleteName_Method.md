---
title: Database.DeleteName Method

Id: DeleteName_Method
TocParent: aerLrfDatabaseMethods
TocOrder: 70


---

**DeleteName** deletes an existing database name from the Application Data folder. 

```

 *database* . **DeleteName**  (ExistingName)
```

#### Parameters

**ExistingName** 

Required. A string containing the name of an existing
                database name to delete from the Application Data
                folder.


### Remarks
This method is **Shared** , and does not affect the current values of the database object. 

Use the [GetNames](GetNames_Method.html) method to get an array of strings containing all of the database names found in the Application Data folder. 

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows server 2012, Windows server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

### See Also
[ASNA.VisualRPG.Runtime](ecrLrfRuntimeNamespace.html)

[Database Class](Date_Formats.html)

[Database Class Members](ecrLrfDatabasePropertiesMain.html)

[Database Class Methods](ecrLrfDatabaseMethods.html)

[Database Class Properties](ecrLrfDatabasePropertiesMain.html)

[DCLDB](DCLDB.html)

[GetNames Method](GetNames_Method.html) 

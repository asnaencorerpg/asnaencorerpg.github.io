---
title: Database.GetNames Method

Id: GetNames_Method
TocParent: aerLrfDatabaseMethods
TocOrder: 80


---

**GetNames** returns an array of strings with all of the names found in the Application Data special folders and the registry (for backward compatibility) 

```
 variable[] = *database* . **GetNames**  (publicDBs)
```

### Parameters

**publicDBs** 

Required.  A boolean parameter indicating whether to get Public
                Databases (*True) or those private to the current user (*False).


### Returns
A string array with all of the names found in the registry.

### Remarks
This method is **Shared** , and does not affect the current values of the database object. 

**Private** Database names are stored in the registry at HKEY_CURRENT_USER\Software\ASNA\Acceler8-DB\CurrentVersion\Databases. 

**Public** Database names are stored in the registry at HKEY_LOCAL_MACHINE\SOFTWARE\ASNA\Acceler8-DB\CurrentVersion\Data Sources\*PUBLIC. 

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows server 2012, Windows server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

### See Also
[ASNA.VisualRPG.Runtime](aerLrfRuntimeNamespace.html)

[Database Class](Date_Formats.html)

[Database Class Members](aerLrfDatabasePropertiesMain.html)

[Database Class Methods](aerLrfDatabaseMethods.html)

[Database Class Properties](aerLrfDatabasePropertiesMain.html)

[DCLDB](DCLDB.html) 

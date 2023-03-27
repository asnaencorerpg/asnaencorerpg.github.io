---
title: Database.PlatformAttribute Property

Id: PlatformAttribute_Property
TocParent: aerLrfDatabasePropertiesMain
TocOrder: 7


---

**PlatformAttribute** gets or sets the platform-specific attribute of the database engine. 

```

 *database* . **PlatformAttribute =** *<stringVal>*  
```

### Property Value
***<stringVal>*** is of type *String and contains the platform-specific attribute of the database engine. 

### Remarks
The **PlatformAttribute** property is used to distinguish between different database engines that can reside on the same machine. For instance, both DataGate for Windows and SQL Server can reside on the same machine. When accessing SQL Server databases, **PlatformAttribute** must be set to "* **SQLOLEDB** ". The setting of assumed "*DATALINK" is used for DataGate for Windows and DataGate for IBM System i. Any value other than "*SQLOLEDB" is presumed to be "*DATALINK". 

The PlatformAttribute property is also used in conjunction with the [CreateName](CreateName_Method.html) and [UpdateName](UpdateName_Method.html) methods. 

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows Server 2012, Windows Server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

### See Also
[ASNA.VisualRPG.Runtime](aerLrfRuntimeNamespace.html)

[Database Class](Date_Formats.html)

[Database Class Properties](aerLrfDatabasePropertiesMain.html)

[Database Class Methods](aerLrfDatabaseMethods.html)

[DCLDB](DCLDB.html)

[CreateName Method](CreateName_Method.html)

[UpdateName Method](UpdateName_Method.html) 

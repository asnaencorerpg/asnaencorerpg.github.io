---
title: Database.CreateName Method

Id: CreateName_Method
TocParent: aerLrfDatabaseMethods
TocOrder: 50


---

**CreateName** takes all the current values of the database name, except for the name itself, and creates a new "Database Name" in the Application Data folder with the name given in **NewName** . 

```

 *database* . **CreateName**  (NewName)
```

### Parameters

**NewName** 

Required. A string containing a new database name to be
                created in the Application Data folder.


### Remarks
**CreateName** creates a new "Database Name" in the registry with the name given in ** *NewName* ** . The content of the Application Data folder database name entries are defined by the values of the [Label](Label_Property.html), [PlatformAttribute](PlatformAttribute_Property.html), [PoolingTimeOut](PoolingTimeOutProperty.html), [Password](Password_Property.html), [Port](Port_Property.html), [Server](Server_Property.html), [Text](TextProperty.html), and [User](User_Property.html) properties. 

You can use the [UpdateName](UpdateName_Method.html) method to write the current values of the database name object as the new values of the database name in the Application Data folder. 

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

[UpdateName Method](UpdateName_Method.html)

[DCLDB](DCLDB.html) 

---
title: Database.UpdateName Method

Id: UpdateName_Method
TocParent: aerLrfDatabaseMethods
TocOrder: 140


---

**UpdateName** takes the current values of the database name object and writes them out as new values of the database name in the Application Data folder. 

```
 *database* . **UpdateName** ()
```

### Remarks
**UpdateName** takes the current values of the database name object and writes them out as new values of the database name in the Application Data folder. 

You can use the [CreateName](CreateName_Method.html) method to take all the current values of the database name, except for the name itself, and create a new "Database Name" in the Application Data folder with the name given in ** *NewName* ** . 

**UpdateName** modifies the "Database Name" in the registry corresponding the name given in the *Dbname* property. The updated content of the Application Data folder entries are defined by the values of the [Label](Label_Property.html), [PlatformAttribute](PlatformAttribute_Property.html), [PoolingTimeOut](PoolingTimeOutProperty.html), [Password](Password_Property.html), [Port](Port_Property.html), [Server](Server_Property.html), [Text](TextProperty.html), and [User](User_Property.html) properties. 

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA.VisualRPG.Runtime(in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows Server 2012, Windows Server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

### See Also
[ASNA.VisualRPG.Runtime](ecrLrfRuntimeNamespace.html)

[Database Class](Date_Formats.html)

[Database Class Members](ecrLrfDatabasePropertiesMain.html)

[Database Class Methods](ecrLrfDatabaseMethods.html)

[Database Class Properties](ecrLrfDatabasePropertiesMain.html)

[DCLDB](DCLDB.html)

[CreateName Method](CreateName_Method.html) 

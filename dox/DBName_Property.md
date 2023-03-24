---
title: Database.DBName Property

Id: DBName_Property
TocParent: aerLrfDatabasePropertiesMain
TocOrder: 1


---

**DBName** gets or sets the **name** of a database. 

```

 *database* 
 **.DBName**  = *<stringVal>* 
```

### Property Value

***<stringVal>***  containing the name of a
                database. 

### Remarks

When set to a valid database name, the referenced database server becomes the
                database object upon connection. Setting the database name is a common means of
                overriding the database connection.  When set to a valid database name,
                the following properties are also set from the collateral content of the
                Database name's registry content: [Label](Label_Property.html), [PlatformAttribute](PlatformAttribute_Property.html), [PoolingTimeOut](PoolingTimeOutProperty.html),
                [Port](Port_Property.html), [Server](Server_Property.html), [Text](TextProperty.html), [User](User_Property.html). 

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows server 2012, Windows server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

### See Also
[ASNA.VisualRPG.Runtime](aerLrfRuntimeNamespace.html)
[Database Class](aerLrfDatabaseClass.html)
[Database Class Members](aerLrfDatabaseMembers.html)
[Database Class Properties](aerLrfDatabasePropertiesMain.html)
[DCLDB](DCLDB.html) 

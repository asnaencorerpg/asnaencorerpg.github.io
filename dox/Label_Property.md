---
title: Database.Label Property

Id: Label_Property
TocParent: aerLrfDatabasePropertiesMain
TocOrder: 5


---

Gets or sets a string containing the label of the database to connect to.

```

 *database* . **Label = *<* ** *stringVal>*  
```

### Property Value
*<stringVal>* of type *String ** containing the label of the database to connect to. 

### Remarks
The **Label** property specifies a particular database instance on the server platform, for platforms that allow more than one server instance, such as DataGate for Windows Server and Microsoft SQL Server. 

For single-instance platforms, such as the System i, the **Label** property is ignored. The **Label** property is also used in conjunction with the [CreateName](CreateName_Method.html) and [UpdateName](UpdateName_Method.html) methods. 

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows Server 2012, Windows Server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

### See Also
[ASNA.VisualRPG.Runtime](aerLrfRuntimeNamespace.html)
[Database Class](Date_Formats.html)
[Database Class Members](aerLrfDatabasePropertiesMain.html)
[Database Class Properties](aerLrfDatabasePropertiesMain.html)
[DCLDB](DCLDB.html)
[CreateName Method](CreateName_Method.html)
[UpdateName Method](UpdateName_Method.html) 

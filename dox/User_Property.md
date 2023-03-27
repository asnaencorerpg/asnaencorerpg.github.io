---
title: Database.User Property

Id: User_Property
TocParent: aerLrfDatabasePropertiesMain
TocOrder: 12


---

**User** gets or sets the authenticated user profile used to authorize the current database connection. 

```

 *database* . **User =** *<stringVal>* 
```

### Property Value
***<stringVal>*** is of type *String containing the authenticated user profile used to authorize the current database connection. 

### Remarks
Authentication is the process of verifying that a user with a unique name is the actual user that the name implies. This verification process is also applied to applications running in the security context of a user. Typically, authentication is implemented by giving the user a [password](Password_Property.html). 

The user profile described by the **User** property is the one used to authenticate the database connection on the server platform, not the client. 

The **User** property is also used in conjunction with the [CreateName](CreateName_Method.html) and [UpdateName](UpdateName_Method.html) methods. 

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA.VisualRPG.Runtime(in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows Server 2012, Windows Server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

### See Also
[ASNA.VisualRPG.Runtime](ecrLrfRuntimeNamespace.html)

[Database Class](Date_Formats.html)

[Database Class Members](ecrLrfDatabasePropertiesMain.html)

[Database Class Properties](ecrLrfDatabasePropertiesMain.html)

[Database Class Methods](ecrLrfDatabaseMethods.html)

[DCLDB](DCLDB.html)

[CreateName Method](CreateName_Method.html)

[UpdateName Method](UpdateName_Method.html)

[Password Property](Password_Property.html) 

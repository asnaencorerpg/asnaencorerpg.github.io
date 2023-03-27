---
title: Database.Password Property

Id: Password_Property
TocParent: aerLrfDatabasePropertiesMain
TocOrder: 6


---

**Password** gets the password used in conjunction with [User](User_Property.html) for connection authentication. 

```

 *<stringVal>* 
 **=** 
 *database* . **Password**  
```

### Property Value
*<stringVal>* is of type *String and contains the password for the user profile indicated by the **User** property. 

### Remarks
Authentication is the process of verifying that a user with a unique name is the actual user that the name implies. This verification process is also applied to applications running in the security context of a user. Typically, authentication is implemented by giving the user a **password** . 

The Password property is also used in conjunction with the [CreateName](CreateName_Method.html) and [UpdateName](UpdateName_Method.html) methods, where the password is stored in the registry as encrypted data. 

This property is only set if the user profile has an associated password, and only after setting the **User** property. 

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

[User Property](User_Property.html) <br /> 

---
title: Database Class

Id: aerLrfDatabaseClass
TocParent: aerLrfRuntimeNamespace
TocOrder: 0


---

The Database class contains the information required to create a database connection. 

For alist of all members of this type, see [Database Members](aerLrfDatabaseMembers.html). 

[ASNA.VisualRPG.Runtime](aerLrfRuntimeNamespace.html) <br /> ASNA.VisualRPG.Runtime. **Database** 

```
 &lt;Serializable&gt;
 **Syntax** 
```

### Thread Safety
This type is safe for multithreaded operations.

### Remarks
To "load" the contents of the registry for a particular database name, set the [DBName](DBName_Property.html) property of the database object declared with [DCLDB](DCLDB.html). If a database name exists with the name, values such as server, label, and user, etc., become current and available through properties of the object. 

You can use the [CreateName](CreateName_Method.html) method to take all the current values of the database name, except for the name itself, and creates a new "Database Name" in the registry with the name given in *NewName* . 

You can use the [UpdateName](UpdateName_Method.html) method to write the current values of the database name object as the new values of the database name in the registry. 

There are two methods which are Shared. These methods don't affect the current values of the database object. 

- [GetNames](GetNames_Method.html) (*Boolean Public Databases) - Returns an array of string with all the names found in the registry. The Boolean parameter indicates whether to get Public Database ( **True** ) or those private to the current user ( **False** ).
- [DeleleteName](DeleteName_Method.html) (*String Existing Name) - This method deletes from the registry an existing database Name.

### Requirements
**Namespace:** ASNA.VisualRPG. Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG. Runtime .dll) 

**Platforms:** Windows server 2012, Windows server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

### See Also
[ASNA.VisualRPG.Runtime](aerLrfRuntimeNamespace.html)
[Database Class Members](aerLrfDatabaseMembers.html)
[DCLDB](DCLDB.html) 

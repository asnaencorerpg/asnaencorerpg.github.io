---
title: Database.Database (string)

Id: Database_DatabaseConstructor
TocParent: aerLrfDatabaseConstructors
TocOrder: 10

---

**Database** initializes a new instance of a [Database](aerLrfDatabaseClass.html) object. 
<pre class="prettyprint">
 **Database (dbName)** 
      </pre>

### Parameters

***dbName*** 

Required string. *dbName* is a character expression containing the name of the actual database you are declaring.


### Remarks
** *dbName* ** is used to "load" the contents of the registry for a particular database name. If a database name exists with the name, values such as server, label, and user, etc., become current and available through properties of this object. 

You can use the [CreateName](CreateName_Method.html) method to take all the current values of the database name, except for the name itself, and creates a new "Database Name" in the registry with the name given in <span class="SpellE"> *NewName* </span>. 

You can use the [UpdateName](UpdateName_Method.html) method to write the current values of the database name object as the new values of the database name in the registry. 

- To get the measurement in millimeters, divide by 100.
- To get the measurement in centimeters, divide by 1,000.
- To get the measurement in inches, divide by 2,540.

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows server 2012, Windows server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

### See Also
[ASNA.VisualRPG.Runtime](aerLrfRuntimeNamespace.html)
[Database Class](aerLrfDatabaseClass.html)
[Database Members](aerLrfDatabaseMembers.html)
[DCLDB](DCLDB.html) 

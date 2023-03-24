---
title: DBFile.MemberName Field

Id: MemberNameFieldDBFileClass
TocParent: aerLrfDbFileFieldsMain
TocOrder: 6


---

**MemberName** contains the name of the file member to be opened when the file is opened. 

```

 *dbfile* . **MemberName Type (*String)** 
```

### Remarks
**MemberName** must be set prior to opening the file (see [OPEN](OPEN.html) command). 

If **MemberName** is not set, the value of the **Mbr** parameter specified in the [DCLDISKFILE](DCLDISKFILE.html) command is used. 

In addition to specifying a named file member, **MemberName** may also be set to the following special values: 

- *FIRST will access the member with the oldest creation date.
- *FILE will access the member name with the same name as the file name.

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows Server 2012, Windows Server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

### See Also
[ASNA.VisualRPG.Runtime](aerLrfRuntimeNamespace.html)
[DBFile Class](aerLrfDBFileClass.html)
[DBFile Class Members](aerLrfDBFileMembers.html)
[DCLDISKFILE](DCLDISKFILE.html)
[OPEN](OPEN.html) 

---
title: DBFile.FilePath Field

Id: FilePathFieldDBFileClass
TocParent: aerLrfDbFileFieldsMain
TocOrder: 2


---

<span> **FilePath** </span> contains a string that specifies the path of the file. 

```

 *dbfile* . **FilePath Type (*String)** 
```

### Remarks
**FilePath** must be set prior to opening a file <span class="GramE">(see</span>[OPEN](OPEN.html) command). 

If **FilePath** is not set, the filepath of the **File** parameter specified in the [DCLDISKFILE](DCLDISKFILE.html) command is used. 

Setting the **FilePath** prior to opening a file is equivalent to the System i process called **override database file** . 

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows server 2012, Windows server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

### See Also
[ASNA.VisualRPG.Runtime](aerLrfRuntimeNamespace.html)

[DBFile Class](aerLrfDBFileClass.html)

[DBFile Members](aerLrfDBFileMembers.html)

[DCLDISKFILE](DCLDISKFILE.html)

[OPEN](OPEN.html) 

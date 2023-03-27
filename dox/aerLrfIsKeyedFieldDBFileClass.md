---
title: DBFile.IsKeyed Field

Id: aerLrfIsKeyedFieldDBFileClass
TocParent: aerLrfDbFileFieldsMain
TocOrder: 5


---

**IsKeyed** contains **True** if the file has been opened for "keyed" access. 

```
 *dbfile* . **IsKeyed Type (*Boolean)** 
```

### Remarks
When the **ChkFmtID** parameter specified in the [DCLDISKFILE](DCLDISKFILE.html) command is set to * **Yes** or * **Same** , **IsKeyed** returns **True** if the format ID of the file specified in the DclDiskfile's **FileDesc** parameter is the same as the file opened at run-time. 

The Encore RPG compiler stores the format of each file in the assembly when a program is compiled. At run-time, ECR can then compare the stored format ID with the format ID of the currently-opened file. 

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows server 2012, Windows server 2012 R2, Windows Server 2016, Windows Vista Business Edition, Windows 7, Windows 8, Windows 10. 

### See Also
[ASNA.VisualRPG.Runtime](aerLrfRuntimeNamespace.html) <br /> <span style="FONT-SIZE: 8pt; FONT-FAMILY: Verdana; mso-bidi-font-family: 'Courier New'"> [DBFile Class](aerLrfDBFileClass.html)

[DBFile Members](aerLrfDBFileMembers.html)

[DCLDISKFILE](DCLDISKFILE.html) </span> 

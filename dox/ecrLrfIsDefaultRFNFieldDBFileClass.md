---
title: DBFile.IsDefaultRFN Field

Id: aerLrfIsDefaultRFNFieldDBFileClass
TocParent: aerLrfDbFileFieldsMain
TocOrder: 3


---

**IsDefaultRFN** contains **True** if the "default" renamed format is going to be used. 

```
 *dbfile* . **IsDefaultRFN Type (*Boolean)** 
```

### Remarks
When the **ChkFmtID** parameter specified in the [DCLDISKFILE](DCLDISKFILE.html) command is set to * **Yes** or * **Same** , **IsDefaultRFN** returns **True** if the format ID of the file specified in the DclDiskfile's **FileDesc** parameter is the same as the file opened at run-time. 

The Encore RPG compiler stores the format of each file in the assembly when a program is compiled. At run-time, ECR can then compare the stored format ID with the format ID of the currently-opened file. 

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows server 2012, Windows server 2012 R2, Windows Server 2016, Windows Vista Business Edition, Windows 7, Windows 8, Windows 10. 

### See Also
[ASNA.VisualRPG.Runtime](ecrLrfRuntimeNamespace.html) <br /> <span> [DBFile Class](ecrLrfDBFileClass.html)

[DBFile Members](ecrLrfDBFileMembers.html)

[DCLDISKFILE](DCLDISKFILE.html) </span> 

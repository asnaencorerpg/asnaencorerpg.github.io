---
title: DBFile.WaitRec Field

Id: WaitRecFieldDBFileClass
TocParent: aerLrfDbFileFieldsMain
TocOrder: 11


---

**WaitRec** contains the waiting period for a record. 

```

 *dbfile* . **WaitRec Type (*Integer)** 
```

### Field Value:
Integer values containing the time to wait for a record. 

### Comments
**WaitRec** must be set prior to opening the file (see [OPEN](OPEN.html) command). 

If **WaitRec** is not set, the value of the ** *WaitRec* ** parameter specified in the [DCLDISKFILE](DCLDISKFILE.html) command is used. The DclDiskFile parameter values are: 

- *FILE (default) - indicates that the properties of the file are used to
                determine how long it waits for the record.
- *IMMEDIATE - it won't wait for a record.
- *NOMAX - it will wait indefinitely.

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA.VisualRPG.Runtime(in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows Server 2012, Windows Server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

### See Also
[ASNA.VisualRPG.Runtime](ecrLrfRuntimeNamespace.html)

[DBFile Class](ecrLrfDBFileClass.html)

[DBFile Members](ecrLrfDBFileMembers.html)

[OPEN](OPEN.html)

[DCLDISKFILE](DCLDISKFILE.html) 

---
title: DBFile.ShareType Field

Id: ShareTypeFieldDBFileClass
TocParent: aerLrfDbFileFieldsMain
TocOrder: 10


---

**ShareType** contains a string defining how a file will be shared when opened. 

```

 *dbfile* . **ShareType Type (*String)** 
```

### Field Values
String value containing one of the following:

- **Exclusive** - File is opened for update, exclusive lock.<br /> This lock can be held by exactly one database session. No other sessions are granted any lock type on the object when an **Exclusive** lock is held, and conversely, the **Exclusive** lock will not be granted if any other type of lock is held in another session. The granted session has exclusive system access to the object.
- **ExclusiveRead** - File is opened for update, other jobs may read.<br /> When this lock is granted, other database sessions may access the object for read-only access, but no other sessions are granted any type of exclusive access. This is appropriate to use when the object should be restricted from any access other than read access.
- **ShareUpdate** - File is opened for update, other jobs may read or update.<br /> When this lock is granted, the object can be accessed for updating or reading by other sessions. When held, other sessions will be granted **ShareRead** or **ShareUpdat** e locks for the same object. This lock prevents **Exclusive** access to the object. This lock type is appropriate when the target object is to be modified in the current session, and read and change access in other sessions should be allowed.
- **ShareNoUpdate** - File is opened for read, other jobs may read.<br /> When this lock is granted, the object can be accessed only for reading by other sessions. When held, other sessions will be granted ShareRead or ShareNoUpdate locks for the same object. This lock prevents exclusive access and update access to the object. This lock type is appropriate when the target object should not be modified by any session, but all sessions should be allowed to read the object.
- **ShareRead** - File is opened for read, other jobs may read or update.<br /> When this lock is granted, the object can be accessed non-exclusively by other sessions. When held, other sessions will be granted **ExlusiveRead** , **ShareUpdate** , **ShareRead** or **ShareNoUpdate** locks for the same object, so long as the lock requested does not conflict with another session's held lock. Alone, this lock prevents only **Exclusive** access. It is appropriate when the target object should not be locked exclusively by any one session.

### Remarks
<p> **ShareType** must be set prior to opening the file (see [OPEN](OPEN.html) command). 

If **ShareType** is not set, the value of the ** *ShareType* ** parameter specified in the [DCLDISKFILE](DCLDISKFILE.html) command is used. 

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA.VisualRPG.Runtime(in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows Server 2012, Windows Server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

### See Also
[ASNA.VisualRPG.Runtime](aerLrfRuntimeNamespace.html)
[DBFile Class](aerLrfDBFileClass.html)
[DBFile Members](aerLrfDBFileMembers.html)
[DCLDISKFILE](DCLDISKFILE.html) 

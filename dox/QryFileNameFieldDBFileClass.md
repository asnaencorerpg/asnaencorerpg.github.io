---
title: DBFile.QryFileName Field

Id: QryFileNameFieldDBFileClass
TocParent: aerLrfDbFileFieldsMain
TocOrder: 7


---

**QryFileName** contains the name of the query file created for the **QrySelect** and **QryKeyFlds** parameters. 

```

 *dbfile* . **QryFileName Type (*String)** 
```

### Remarks
**QryFileName** must be set prior to opening the file (see [OPEN](OPEN.html) command). 

If **QryFileName** is not set, the value of the **QryFileName** parameter specified in the [DCLDISKFILE](DCLDISKFILE.html) command is used. 

**QryFileName** specifies the name of the query file created for DCLDISKFILE's **QrySelect** and **QryKeyFlds** parameters. If *NAME is specified, which is the default, the file name given in the DCLDISKFILE command is used. 

If the database access with this file is System i database, then the **QryFileName** is used both on the **OVRDBF** and the **OPNQRYF** commands used when opening the file. 

For a DataGate for Windows database, a temporary logical file is created in QTemp with the **QryFileName** as its name. You can use the special name * **UNIQUE** to guarantee that there will be no conflicts with other files residing in QTemp. You will receive errors if there are duplicate file names in QTemp. 

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows Server 2012, Windows Server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

### See Also
[ASNA.VisualRPG.Runtime](ecrLrfRuntimeNamespace.html)

[DBFile Class](ecrLrfDBFileClass.html)

[DBFile Members](ecrLrfDBFileMembers.html)

[DCLDISKFILE](DCLDISKFILE.html)

[QryKeyFlds Field](QryKeyFldsFieldDBFileClass.html)

[QrySelect](QrySelectFieldDBFileClass.html) 

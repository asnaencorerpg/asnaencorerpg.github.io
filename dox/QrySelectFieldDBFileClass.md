---
title: DBFile.QrySelect Field

Id: QrySelectFieldDBFileClass
TocParent: aerLrfDbFileFieldsMain
TocOrder: 9


---

**QrySelect** contains the selection expression used to determine which records are to be made available for processing. 

```

 *dbfile* . **QrySelect Type (*String)** 
```

### Remarks
**QrySelect** must be set prior to opening the file (see [OPEN](OPEN.html) command). 

If **QrySelect** is not set, the value of the **QrySelect** parameter specified in the [DCLDISKFILE](DCLDISKFILE.html) command is used. 

[QryKeyFlds](QryKeyFldsFieldDBFileClass.html) is used in conjunction with **QrySelect** to specify ordering of the selected records. Use [QryFileName](QryFileNameFieldDBFileClass.html) to specify the name of the temporary query file created. 

**When using QrySelect, please Note:** 

- *NONE (default) - there is no selection expression available for processing.
- Selection expressions are evaluated during file open time.  Therefore, a
                run-time error will be generated during the opening of the file when a
                selection expression error is encountered.
- The Select statement syntax can vary depending upon the syntax supported by the
                target database engine.  Each key field is composed of a field name
                followed by optional attributes that determine the sorting order (ascending,
                descending, or absolute value for numeric fields).
- QrySelect statements can be no longer than 2000 characters. Any statement exceeding
                this limit will throw an error.

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows Server 2012, Windows Server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

### See Also
[ASNA.VisualRPG.Runtime](aerLrfRuntimeNamespace.html)
[DBFile Class](aerLrfDBFileClass.html)
[DBFile Members](aerLrfDBFileMembers.html)
[DCLDISKFILE](DCLDISKFILE.html)
[QryFileName Field](QryFileNameFieldDBFileClass.html)
[QryKeyFlds Field](QryKeyFldsFieldDBFileClass.html) 

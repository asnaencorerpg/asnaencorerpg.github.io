---
title: DBFile.QryKeyFlds Field

Id: QryKeyFldsFieldDBFileClass
TocParent: aerLrfDbFileFieldsMain
TocOrder: 8


---

**QryKeyFlds** contains the name of one or more key fields used to arrange the query records. 

```

 *dbfile* . **QryKeyFlds Type(*String)** 
```

### Remarks
When you use **QryKeyFlds** , the file sequence is changed to your new specification. This means that keyed operations for **SETLL** , **SETGT** , **CHAIN** , **READRAND** , **READE** , **READPE** , **READRANGE** and **SETRANGE** can result in undesirable or unpredictable results. To ensure that inadvertent use of keyed operations is not allowed, set the **dclDiskFile** ’s **Random** keyword value to *NO. 

**QryKeyFlds** must be set prior to opening the file (see [OPEN](OPEN.html) command). 

If **QryKeyFlds** is not set, the value of the **QryKeyFlds** parameter specified in the [DCLDISKFILE](DCLDISKFILE.html) command is used. 

Each key field is composed of a field name followed by optional attributes that determine the sorting order (ascending descending, or absolute value for numeric fields). 

- *FILE - is the default, which specifies that the value of the **QryKeyFlds** 
                parameter specified in the **DCLDISKFILE** 
                command is used.
- *NONE - specifies that the file has no keys.
- A string containing key field name(s) and corresponding sort attributes that
                determine the sorting order (ascending, descending, or absolute value for
                numeric fields).<br /> **Syntax** : The syntax for the QryKeyFlds string is:
                <br />
                ( KeyFieldName1 Attributes  KeyFieldName2 Attributes … KeyFieldNamen
                Attributes )

KeyFieldName must be a valid field name in the file. Attributes consist of the following: * **ASCEND** , * **DESCEND** , or * **ABSVAL** . You can have as many attributes as you want after a field name as long as they conform to the rules below. 

1. Each key field name and attribute must be separated by at least one blank.
2. *ASCEND and *DESCEND cannot be applied to the same field.
3. *ABSVAL only applies to numeric fields.

If there are any errors in the key fields' expression, they will not be detected until the file is opened at run-time. 

Use [QrySelect](QrySelectFieldDBFileClass.html) in conjunction with **QryKeyFlds** to specify the selection criteria indicating which records to select from a file. Use [QryFileName](QryFileNameFieldDBFileClass.html) to specify the name of the temporary query file created. Selection expressions are evaluated during file open time. Therefore, a runtime error will be generated during the opening of the file when a selection expression error is encountered. 

**Example** 
<code class="language-aer">
            myFile.QryKeyFlds = "CMActive *DESCEND CMState *ASCEND CMCity
            *ASCEND CMFax *ABSVAL *DESCEND"
        ```

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

[QrySelect Field](QrySelectFieldDBFileClass.html) 

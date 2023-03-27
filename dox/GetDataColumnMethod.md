---
title: MemoryFile.GetDataColumn Method

Id: GetDataColumnMethod
TocParent: aerLrfMemoryFileMethodsMain
TocOrder: 0


---

Returns a **System.Data.DataColumn** object from the given table and column. 

```

 **MemoryFile.GetDataColumn(**  TableName, ColumnName **)** 
```

### Parameters

**TableName** 

The name of the table in the memoryfile dataset. E.g., if an external file
                definition was used to describe the memory file, the name would then be the
                record format name from the description.


**ColumnName** 

The name of the column in the memoryfile's TableName. E.g., if an external file
                definition was used to describe the memory file, the name would then be the
                field name.


### Remarks
Use **GetColumnName** whenever you need to retrieve the schema of a DataTable column. 

When accessing **DataTable** objects, note that they are conditionally case-sensitive. For example, if one **DataTable** is named "mydatatable" and another is named "Mydatatable", a string used to search for one of the tables is regarded as case-sensitive. However, if "mydatatable" exists and "Mydatatable" does not, the search string is regarded as case-insensitive. 

### See Also
[ASNA.VisualRPG.Runtime](ecrLrfRuntimeNamespace.html)

[MemoryFile Class](ecrLrfMemoryFileClass.html)

[MemoryFile Class Members](ecrLrfMemoryFileMembers.html)

[DCLMEMORYFILE](DATE_Function.html) 

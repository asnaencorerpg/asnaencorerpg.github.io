---
title: COMMIT

Id: COMIT
TocParent: aerLrfOpCodesMain
TocOrder: 310


---

**COMMIT** performs the following functions: 

- Makes all the changes to your files that have been specified in output operations since the previous **COMMIT** or [ROLLBACK](ROLBACK.html) operation.
- Releases all the record locks for files you have under commitment control.


```

 **COMMIT** 
 **Db**  (Database Object)
Marker (<u>*NONE</u> | Boundary)
Err (Indicator Variable | *EXTENDED)
```

### Parts

**Db** 

**Required** . The database connection for which transaction is to be committed. Database Objects are defined with the [DCLDB](DCLDB.html) command.


**Marker** 

Optional. Allows you to specify a literal, named constant, array element, table name, data structure, or data structure subfield to identify the boundary between the changes made by this **COMMIT** operation and subsequent changes. If you leave Marker blank (or use default of *NONE), the identifier is null.


**Err** 

Optional. Determines what the runtime will do if an error occurs while executing this command. The following rules apply: 

- **Err** (Indicator Variable) - The specified Indicator is set if an error occurred.
- **Err** (*EXTENDED) - A program status flag is set whose status can be checked using the [%ERROR](ERROR_Function.html) built-in function.
- If the **Err** keyword is not given and an error occurs, a runtime exception will be thrown.


### Remarks
The file changes and the record-lock releases apply to all the files you have under commitment control for the specified database connection. 

**COMMIT** and **ROLLBACK** operations are supported for the System i DB2/400 and Windows SQL Server database engines. The **COMMIT** / **ROLLBACK** operations only apply to database files opened with the **COMMIT** (*YES) parameter. 

**Important** : *You **must** start and end commitment control on SQL Server and System i with the* [*STARTTPM*](STARTTPM.html) *and* [*ENDTPM*](ENDTPM.html) *commands from your application. For the System i, do not employ the STRCMTCTL and ENDCMTCTL commands.* 

### See Also
[DCLDB](DCLDB.html)

[ENDTPM](ENDTPM.html)

[ROLLBACK](ROLBACK.html)

[STARTTPM](STARTTPM.html)

[Using Commitment Control](Comittment_Control.html) 

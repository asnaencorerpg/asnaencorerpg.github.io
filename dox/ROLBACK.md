---
title: ROLLBACK

Id: ROLBACK
TocParent: aerLrfOpCodesMain
TocOrder: 1400


---

**ROLLBACK** performs several functions: 

- Cancels all the changes to your files that have been specified in output operations to files under commitment control since the previous [COMMIT](COMIT.html) or **ROLLBACK** operation.
- Repositions the file to its position at the time of the previous **COMMIT** operation (or at the time of the file [OPEN](OPEN.html), if there has been no previous **COMMIT** operation.)
- Releases all record locks for the files you have under commitment control.


```

 **ROLLBACK** 
 **Db**  (Database Object)
Err (Indicator Variable | *EXTENDED)
```

### Parts

**Db** 

**Required** . The database connection for which transaction is to be rolled back. Database Objects are defined with the [DCLDB](DCLDB.html) command.


**Err** 

Optional. Determines what the runtime will do if an error occurs while executing this command. The following rules apply: 

- **Err** (Indicator Variable) - The specified Indicator is set if an error occurred.
- **Err** (*EXTENDED) - A program status flag is set whose status can be checked using the [%ERROR](ERROR_Function.html) built-in function.
- If the **Err** keyword is not given and an error occurs, a runtime exception will be thrown.


### Remarks
The file changes are eliminated to all the file you have under commitment control for the specified database connection. 

**COMMIT** and **ROLLBACK** operations are supported for the System i DB2/400 and Windows SQL Server database engines. The **COMMIT** / **ROLLBACK** operations only apply to database files opened with the **COMMIT** (*YES) parameter. 

**Important** : *You **must** start and end commitment control on SQL Server and System i with the* [*STARTTPM*](STARTTPM.html) *and* [*ENDTPM*](ENDTPM.html) *commands from your application. For the System i, do not employ the STRCMTCTL and ENDCMTCTL commands.* 

### See Also
[COMMIT](COMIT.html)
[DCLDB](DCLDB.html)
[ENDTPM](ENDTPM.html)
[OPEN](OPEN.html)
[STARTTPM](STARTTPM.html)
[Using Commitment Control](Comittment_Control.html) 

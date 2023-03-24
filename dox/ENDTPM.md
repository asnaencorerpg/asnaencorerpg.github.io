---
title: ENDTPM

Id: ENDTPM
TocParent: aerLrfOpCodesMain
TocOrder: 940


---

<span style="FONT-WEIGHT: bold">ENDTPM</span> is used to end the transaction processing monitor on the specified data source. If there are uncommitted changes, the changes are [rolled back](ROLBACK.html). 

```

 **ENDTPM** 
 **Db**  (Database Object)
Err (Indicator Variable | *EXTENDED)
```

### Parts

**Db** 

**Required** . The database connection for which transaction processing is to be ended. Database Objects are defined with the [DCLDB](DCLDB.html) command.


**Err** 

Optional. Determines what the runtime will do if an error occurs while executing this command. The following rules apply:


- Err (Indicator Variable) - The specified Indicator is set if an error occurred.
- Err (*EXTENDED) - A program status flag is set whose status can be checked using the [%ERROR](ERROR_Function.html) built-in function.
- If the Err keyword is not given and an error occurs, a runtime exception will be thrown, terminating the program.


### Remarks
**Important** : *You must start and end commitment control on SQL Server and System i with the* [*STARTTPM*](STARTTPM.html) *and* ***ENDTPM** commands from your application. For the System i, do not employ the STRCMTCTL and ENDCMTCTL commands.* 

### See Also
[COMMIT](COMIT.html)
[DCLDB](DCLDB.html)
[ROLLBACK](ROLBACK.html)
[STARTTPM](STARTTPM.html)
[Using Commitment Control](Comittment_Control.html) 

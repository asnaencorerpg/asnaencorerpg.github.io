---
title: STARTTPM

Id: STARTTPM
TocParent: aerLrfOpCodesMain
TocOrder: 1500


---

The **STARTTPM** (Start Transaction Processing Monitor) op code is used to establish a commitment definition. This command specifies the level of record locking that occurs for the commitment definition to be started. You can specify some text that briefly describes the commitment definition to be started. 

```

 **STARTTPM** 
 **Db**  (Database Object)
Level ( <u>*LOW</u> | *MEDIUM | *HIGH | *SERIAL)
Text (<u>*NONE</u> | Character Expression)
ExtraParms (Parm List)
Err (Indicator Variable | *EXTENDED)
```

### Parts

**Db** 

**Required** . The database connection for which transaction processing is to be started. Database Objects are defined with the [DCLDB](DCLDB.html) command.


**Level** 

Optional. Specify the level of record locking that occurs for the commitment definition to be started.

- *LOW - *CHG ReadUncommited - Do not issue shared locks and do not honor exclusive locks. When this option is in effect, it is possible to read an uncommitted transaction or a set of pages that are rolled back in the middle of a read. Dirty reads are possible.
- *MEDIUM - *CS ReadCommited - Perform a scan with the same locking semantics as a transaction running at the READ COMMITTED isolation level. By default, SQL Server 2000 operates at this isolation level.
- *HIGH - *ALL RepeatableRead - Perform a scan with the same locking semantics as a transaction running at the REPEATABLE READ isolation level.
- *SERIAL - *ALL Serializable - Hold a shared lock until completion of the transaction instead of releasing the lock as soon as the required table, row, or data page is no longer required.


**Text** 

Optional. Specify some text that briefly describes the commitment definition to be started.


**ExtraParms** 

Optional. Specify some extra parameters to be used with an iSeries database. This keyword has no effect with non-iSeries databases.


When running STARTTPM against an iSeries database, the ExtraParms keyword is a string which may be used to specify optional parameters to the iSeries STRCMTCTL CL command.


DataGate/400 executes STRCMTCTL on behalf of the ECR program invoking STARTTPM. By default (when ExtraParms is not specified or is an empty string), STRCMTCTL is called with the LCKLVL, TEXT, and CMTSCOPE parameters. You may specify other parameters to STRCMTCTL, e.g., for journaling or other requirements, with the ExtraParms parameter. You must specify each parameter name and value, as you would if using the parameters with STRCMTCTL. For example, to specify a journaling application scenario, you could set ExtraParms as follows:


```
    extrparms = "DFTJRN(*LIBL/MYJRN) OMTJRNE(*NONE)" 
```


Note that DataGate/400 simply appends the value of ExtraParms to the command string invoking STRCMTCTL, so that any syntax errors in the ExtraParms string will result in the failure of the iSeries command.


**Err** 

Optional. Determines what the runtime will do if an error occurs while executing this command. The following rules apply:


- Err (Indicator Variable) - The specified Indicator is set if an error occurred.
- Err (*EXTENDED) - A program status flag is set whose status can be checked using the [%ERROR](ERROR_Function.html) built-in function.
- If the Err keyword is not given and an error occurs, a runtime exception will be thrown, terminating the program.


### Remarks
**Important** : *You must start and end commitment control on SQL Server and System i with the* ***STARTTPM*** *and* [*ENDTPM*](ENDTPM.html) *commands from your application. For the System i, do not employ the STRCMTCTL and ENDCMTCTL commands.* 

When running commitment control on the System i with DataGate, transaction processing **must be started** with the **STARTTPM** command. The ECR runtime uses the **AdgTransaction** object to initiate and control transactions. If you initiate commitment control commands via **CALL/Parm** , the runtime has no knowledge of the server transaction, and as a result, you will receive an exception in the **Commit** and **Rollback** statements. 

### See Also
[COMMIT](COMIT.html)

[DCLDB](DCLDB.html)

[ENDTPM](ENDTPM.html)

[ROLLBACK](ROLBACK.html)

[Using Commitment Control](Comittment_Control.html) 

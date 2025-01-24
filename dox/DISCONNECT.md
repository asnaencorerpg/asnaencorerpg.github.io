---
title: DISCONNECT

Id: DISCONNECT
TocParent: aerLrfOpCodesMain
TocOrder: 670


---

Closes a connection to a database.

```
DISCONNECT 
 Db  (Database Object)
Err (Indicator Variable | *EXTENDED)
```

### Parameters

**Db** 

**Required** . A Database Object defined with the [DCLDB](DCLDB.html) command.


**Err** 

Optional. Determines what the runtime will do if an error occurs while executing this command. The following rules apply: 

- **Err** (Operand) - the name of the err variable.
- **Err** (*EXTENDED) - a program status flag is set whose status can be checked using the [%ERROR](ERROR_Function.html) built-in function.
- If the **Err** keyword is not given and an error occurs, a runtime exception will be thrown.


### Remarks
To open a connection to a database, use [CONNECT](CONNECT.html).

### See Also
[CONNECT](CONNECT.html) 

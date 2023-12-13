---
title: CONNECT

Id: CONNECT
TocParent: aerLrfOpCodesMain
TocOrder: 340


---

Opens a connection to the specified Database object.

```
CONNECT 
 Db  (Database Object)
Err (Indicator Variable | *EXTENDED)
```

### Parts

**Db** 

Required. A Database Object defined with the [DCLDB](DCLDB.html) command.


**Err** 

Optional. Err determines what the runtime will do if an error occurs while executing this command. The following rules apply: 

- **Err** (Indicator Variable) - The specified Indicator is set if an error occurred.
- **Err** (*EXTENDED) - A program status flag is set whose status can be checked using the [%ERROR](ERROR_Function.html) built-in function.
- If the **Err** keyword is not given and an error occurs, a runtime exception will be thrown.


### Remarks
To close the connection to the database, use [DISCONNECT](DISCONNECT.html).

### See Also
[DCLDB](DCLDB.html)

[DCLDISKFILE](DCLDISKFILE.html)

[DISCONNECT](DISCONNECT.html)

[%ERROR](ERROR_Function.html) 

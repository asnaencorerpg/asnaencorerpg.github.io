---
title: CALLB
description: "Call a Bound Procedure "
---


CALLB - Call a Procedure**

Used to call [BEGPROC](BEGPROC.html) procedures.

## Syntax

```
CALLB
        Proc (<Class or Class.Procedure or Procedure name>)
        ParmList (*NONE| Parameter List Name)
        Err (Indicator Variable | *EXTENDED)
        LR (Indicator Variable)
```

## Parameters

**Proc**

**Required**. Proc specifies the name of the class and/or procedure to call. If **Proc** contains a **class** name, then the **Entry** BegProc in that class is called.

**ParmList**

Optional. ParmList specifies the parameter list name. \*NONE is the default and indicates that there is not a parameter list.

If a ParmList is not given, **CALLB** *may* be followed by a group of <https://docs.asna.com/documentation/Help150/AVR/_HTML/DCLPARM.htm> commands specifying the parameters to be passed to the procedure. If a parameter is going to be omitted (the corresponding DclSrParm has the **OMIT** option), use the special value **OMIT** in the **DCLPARM's** name.

**Err**

Optional. Err determines what the runtime will do if an error occurs while executing this command. The following rules apply:

*   **Err** (Indicator Variable) - the specified Indicator is set if an error occurred.
*   **Err** (\*EXTENDED) - the program status flag is set whose status can be checked using the <https://docs.asna.com/documentation/Help150/AVR/_HTML/ERROR_Function.htm> built-in function.
*   If the **Err** keyword is not given and an error occurs, a runtime exception will be thrown.

**LR**

Optional. The specified indicator is set to the value of **INLR** of the called procedure.

## Remarks

Because a procedure may return a value, you may also use a free-form expression to invoke procedures:

   \<procedure name>(Comma-separated parameter list)  
   e.g. `MyProc( CustName, *Omit )`

## Example

```
// Call to a procedure with a ParmList.
              CallB Proc(MyProcedure) ParmList(Listout)

// Call to a procedure with parameters.
              CallB Proc(MyProcedure)
              DclParm CustName(*Omit)
              DclParm CustPhone(*Omit)
```

## See Also

[BEGPROC](BEGPROC.htm>)
[CALLD](CALLD.htm>)
[DCLPARM](DCLPARM.htm>)

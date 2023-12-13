---
title: EVALR

Id: EVALR
TocParent: aerLrfOpCodesMain
TocOrder: 990


---

Evaluates the assignment expression with right-adjust.

```
 EVALR
F2  (Assignment Expression)
Err (Indicator Variable | *EXTENDED)
```

### Parts

**F2** 

Required. Must contain a character assignment expression.


**Err** 

Optional. Determines what the runtime will do if an error occurs while executing this command. The following rules apply: 

- **Err** (Indicator Variable) - The specified Indicator is set if an error occurred.
- **Err** (*EXTENDED) - A program status flag is set whose status can be checked using the [%ERROR](ERROR_Function.html) built-in function.
- If the **Err** keyword is not given and an error occurs, a runtime exception will be thrown.


### Remarks
Use **EVALR** to capture errors in an expression and be notified by the setting of the error indicator, such as: 

```
   EVALR F2(object.method(x, y, z)) Err (*IN88)
```

**Examples of errors are:** 

- Divide by zero.
- Error on a method call.

### Example

```
EVALR X=(A+B)/C 

// Evaluate an expression to determine if the user pressed **Cancel** 

 EVALR F2(MAPIMessages1.SHOW(0)) Err (*IN01)
   IF *IN01
     MsgBox ("User pressed Cancel")
   EndIf
```


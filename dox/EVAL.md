---
title: EVAL

Id: EVAL
TocParent: aerLrfOpCodesMain
TocOrder: 980


---

Evaluates an expression. Is useful for trapping errors.

```
EVAL
F2 (Expression, Assignment Expression)
Adj (<u>*TRUNC</u> | *RNDUP)
Err (Indicator Variable | *EXTENDED)
```

### Parts

**F2** 

Required. Must contain an expression or assignment expression.


**Adj** 

Optional. Indicates half-adjust for numeric expressions. Use **Adj** (*RNDUP) if you wish to round up or **Adj** (*TRUNC) if you wish to truncate the value of the Result. *TRUNC is the default.


**Err** 

Optional. Determines what the runtime will do if an error occurs while executing this command. The following rules apply: 

- **Err** (Indicator Variable) - The specified Indicator is set if an error occurred.
- **Err** (*EXTENDED) - A program status flag is set whose status can be checked using the [%ERROR](ERROR_Function.html) built-in function.
- If the **Err** keyword is not given and an error occurs, a runtime exception will be thrown.


### Remarks
Use **EVAL** to capture errors in an expression and be notified by the setting of the error indicator, such as: 
<pre class="prettyprint">   Eval F2(object.method(x, y, z)) Err (*IN88)</pre>

**Examples of errors are:** 

- Divide by zero.
- Error on a method call.

### Example

```

 **EVAL X=(A+B)/C 05** 
  // Evaluate an expression to determine if the user pressed **Cancel** Eval F2(MAPIMessages1.SHOW(0)) Err (*IN01)
   IF *IN01
     MsgBox ("User pressed Cancel")
   EndIf
```


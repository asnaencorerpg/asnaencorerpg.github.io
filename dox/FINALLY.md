---
title: FINALLY

Id: FINALLY
TocParent: aerLrfOpCodesMain
TocOrder: 1070


---

You can use the [TRY...CATCH...FINALLY](TRYCATCHFINALLY.html) statements for structured exception handling. This allows you to execute a particular block of statements if a specified exception occurs while your code is running. When this happens, the code is said to [THROW](THROW.html) the exception, and you ***catch*** it with the appropriate **CATCH** command. 

```

 **FINALLY** 
        
```

### Remarks
The **TRY** statements are executed first. If no exception occurs, execution continues after the [ENDTRY](ENDTRY.html). 

If an exception occurs, then the systems tries to match the exception to the exception types in the **FINALLY** commands. The first one that matches causes the exception to be "trapped" and the catch statements in the matched **FINALLY** to be executed. If the exception is trapped by a **FINALLY** then after the catch statements are executed, control goes to the next statement after the **ENDTRY** . 

If a **FINALLY** command is present, then the finally statements will always be executed at the end of the **TRY/CATCH** sequence or **TRY** /untrapped exception, no matter what. 

**Rules:** 

- The **only**  branching commands allowed inside a **TRY/CATCH** 
                block are [ITERATE](ITERATE.html), and [LEAVESR](LEAVESR.html).  Any
                other branching command (CAB, GOTO, etc.) is not allowed in this context. 
                It is also illegal to branch out of a FINALLY clause (i.e., you cannot use any
                of the branching commands (ITERATE, CAB, LEAVESR, GOTO, etc) in the body of a
                FINALLY clause.
- The exception Type MUST derive from **System.Exception**  (the
                mother of all exceptions).  A **CATCH**  with a **System.Exception** 
                type will trap **all** 
                exceptions.
- If you have several **CATCH**  commands, the **Name**  must
                be different at this time.

**Example** 

```
BEGSR TryCatch access(*public)
  Dclfld myFld Type(System.Windows.Forms.Button)
  Dclfld myInt *integer 4
  TRY
       myFld.Show()
       myInt = myInt / 0 
  CATCH name( z ) type( System.DivideByZeroException )
    msgbox msg( "by 0" ) Title( z.Message )
  CATCH name( e ) type( System.Exception )
    msgbox msg( "You can't do that!!!" ) Title( e.Message )
 **FINALLY** 
    msgbox "Wow, this works..." 
  ENDTRY
    msgbox "All is well!"
ENDSR
```

### See Also
[CATCH](CATCH.html)
[ENDTRY](ENDTRY.html) 

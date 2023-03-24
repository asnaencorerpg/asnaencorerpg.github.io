---
title: TRY..CATCH..FINALLY

Id: TRYCATCHFINALLY
TocParent: aerLrfOpCodesMain
TocOrder: 16712


---

Provides a way to trap possible errors that may occur in code segments, while still running code. 

```

 **TRY** 
 < **Try statements** >
[CATCH [Name( <exception field name> )] Type( <exception type> )
     [<Catch statements>]
[CATCH ... 
       ... 
]] 
[FINALLY 
     <Finally statements>
]
 **ENDTRY** 
```

### Parts

**Try statements** 

Required.  Statement(s) where an error can occur.


**CATCH** 

Optional.  Multiple [CATCH](CATCH.html) blocks are
                permitted.  If an exception occurs while processing the [TRY](TRY.html)
                block, each **Catch**  statement is examined in textual order to
                determine if it handles the exception.  The identifier specified
                in a **Catch**  clause represents the exception that has been thrown. 
                The identifier is considered to be declared within the **Catch**  block's
                local declaration space.

A **Catch** clause with no identifier will catch all exceptions derived from **System.Exception** . A **Catch** clause with an identifier will only catch exceptions whose types are the same as or derived from the type of the identifier. The type must be **System.Exception** or a type derived from **System.Exception** . 

If a **Catch** clause handles the exception, execution transfers to the **Catch** block. At the end of the **Catch** block, execution transfers to the first statement following the **TRY** statement. The **TRY** statement will not handle any exceptions thrown in a **Catch** block. If no **Catch** clause handles the exception, execution transfers to a location determined by the .NET Framework.


**Name** 

Optional.  Any variable name to refer to the trapped exception object.


**Type** 

Optional.  Specifies the type of class filter.  If the value of **Name** 
                is of the type specified by **Type**  or of a derived type, the
                identifier becomes bound to the exception object.


**Catch** 
 **statements** 

Optional.  Statement(s) to handle errors occurring in the associated **TRY** 
                block.


**FINALLY** 

Optional.  A [FINALLY](FINALLY.html) block is always executed
                when execution leaves any part of the **TRY**  command.

When an exception occurs, execution stops and control is given to the closest exception handler. This often means that lines of code you expect to always be called are not executed. Some resource cleanup, such as closing a file, must always be executed even if an exception is thrown. To accomplish this, you can use a finally block. A finally block is always executed, regardless of whether an exception is thrown.


**Finally** 
 **statements** 

Optional.  Statement(s) that are executed after all other error processing has occurred.


**ENDTRY** 

Required.  Terminates the **TRY...CATCH...FINALLY**  structure.


### Remarks
The **Try Statements** are executed. If no exception occurs, execution continues after the **ENDTRY** (*). If an exception occurs, the systems tries to match the exception to the exception types in the **CATCH** commands. The first one that matches causes the exception to be "trapped" and the catch statements in the matched **CATCH** to be executed. If the exception is trapped by a **CATCH** , then after the catch statements are executed, control goes to the next statement after the **ENDTRY** (*). If a **FINALLY** command is present, then the finally statements will always be executed at the end of the **TRY** / **CATCH** sequence or **TRY** /untrapped exception, no matter what. In the **CATCH** command, the Name is optional. It is used to refer to the trapped exception object. The catch statements are also optional. 

**Rules:** 

- The only branching commands allowed inside a **TRY/CATCH**  block
                are [LEAVE](LEAVE.html), [ITERATE](ITERATE.html), and [LEAVESR](LEAVESR.html).  Any other branching command (CAB, GOTO, etc.) is
                not allowed in this context.   It is also illegal to branch out of a **FINALLY**  clause (i.e., you cannot use any of the branching commands
                ( **ITERATE** , **CAB** , **LEAVESR** , **GOTO** ,
                etc) in the body of a **FINALLY** 
                clause.
- The exception Type MUST derive from **System.Exception**  (the
                mother of all exceptions).  A **CATCH**  with a **System.Exception** 
                type will trap **all** 
                exceptions.
- If you have several **CATCH**  commands, the **Name**  must
                be different at this time.

**Example** 

```

BEGSR TryCatch access(*public)
    dclfld googoo Type(System.Windows.Forms.Button)
    dclfld myInt *integer 4 
 **TRY** 
    googoo.Show() 
    myInt = myInt / 0 
 **CATCH**  name( z ) type( System.DivideByZeroException ) 
    msgbox msg( "by 0" ) Title( z.Message ) 
 **CATCH**  name( e ) type( System.Exception )
    msgbox msg( "You can't do that!!!" ) Title( e.Message )  
 **FINALLY** 
    msgbox "wow, this works..."
ENDTRY
    msgbox "all is well" <br />ENDSR
```

### See Also
[CATCH](CATCH.html)
[ENDTRY](ENDTRY.html)
[FINALLY](FINALLY.html)
[LEAVE](LEAVE.html)
[ITERATE](ITERATE.html)
[LEAVESR](LEAVESR.html)
[THROW](THROW.html)
[TRY](TRY.html) 

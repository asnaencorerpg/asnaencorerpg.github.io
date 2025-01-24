---
title: OSEXEC

Id: OsExec
TocParent: aerLrfOpCodesMain
TocOrder: 1290


---

The **OSEXEC** command opens or prints a specified file. The file can be an executable file or a file that is associated with a program. 

```
OSEXEC 
CmdLine  (Character Expression)
ShowType (<u>*SHOWNORMAL</u> | *HIDE | *MINIMIZED | *RESTORE | *SHOW | *SHOWMAXIMIZED | *SHOWMINIMIZED |
        *SHOWNA | *SHOWNOACTIVE | *SHOWNORMAL)
RtnCode (Numeric Field)
Err (*EXTENDED | Indicator Variable)
Type (<u>*NONE</u> | *BINARY | *BOOLEAN | *BYTE | *CHAR | *FLOAT | *FLOAT4 | *FLOAT8 | *IND | *INTEGER |
      *INTEGER2 | *INTEGER4 | *INTEGER8 | *ONECHAR | *PACKED | *ZONED)
Len (Length Integer, [Decimal Positions Integer])
Operation (<u>*OPEN</u> | *PRINT | *EXPLORE)
Directory (Character Expression)
Wait (<u>*NO</u> | *YES | Indicator Expression)
ExitCode(Numeric Variable)  
```

### Parameters

**CmdLine** 

Required. Specifies the file to open or print, or the folder to open or explore. The function can be either an executable file or a document file. It can also print a document file. **CmdLine** must contain the complete path of the application to execute. 

If the application is being called from a folder that has an embedded blank in the path name, it must be contained within double quotes. There are several ways in which this can for coded, for example: 
<pre class="prettyprint">	OSEXEC "C:\bin\Sysmeter.exe Parm1 Parm2"
	OSEXEC "...\Program Files\Examples\Calculator.EXE"
	OSEXEC ""...\Program Files\Examples\Calculator.EXE""
	OSEXEC """Program Files\Examples\Calculator.EXE"""
	OSEXEC """Program Files\Examples\Calculator.EXE"""	</pre>


**ShowType** 

Optional. Specifies how the application is to be shown when it is open. The default for **ShowType** , if none is specified, is *ShowNormal. The parameter can be one of the following values: 

- *ShowNormal - Activates and displays a window.  If the window is minimized
                        or maximized, windows restores it to its original size and position.
- *Hide - Hides the window and activates another window.
- *Maximize - Maximizes the specified window.
- *Minimize - Minimizes the specified window, and activates the next top-level
                        window in the system's list.
- *Restore - Activates and displays a window. If the window is minimized or
                        maximized, windows restores it to its original size and position.
- *Show - Activates a window and displays it in its current size and position.
- *ShowDefault - Sets the initial show state of its main window.
- *ShowMaximized - Activates a window and displays it as a maximized window.
- *ShowMinimized - Activates a window and displays it as a minimized window.
- *ShowMinNoActive - Displays a window as a minimized window. The active window
                        remains active.
- *ShowNA - Displays a window in its current state. The active window remains
                        active.
- *ShowNoActivate - Displays a window in its most recent size and position. The
                        active window remains active.

If **CmdLine** specifies a document file, **ShowType** should be 0.


**RtnCode** 

Optional. Returns a value greater than 32 if successful, or an error value that is less than or equal to 32 otherwise. The following table lists the error values. The value of the return code is set by Windows. If there was no error, the contents of **RtnCode** are without meaning. For further information, see [%ERROR](http://msdn.microsoft.com/library/default.asp?url=/library/en-us/shellcc/platform/shell/reference/functions/shellexecute.asp"> http://msdn.microsoft.com/library/default.asp?url=/library/en-us/shellcc/platform/shell/reference/functions/shellexecute.asp </a>. 

- 0 = System is either out of memory or resources.
- 2 = The specified file was not found.
- 3 = The specified path was not found.
- 5 = The operating system denied access to the specified file.
- 8 = Insufficient memory to start the application.
- 11 = The executable file was invalid, either it was not a windows applications,
                        or
- 26 = A sharing violation has occurred.
- 27 = The filename association is incomplete or invalid.
- 28 = The DDE transaction could not be completed because the request timed-out.
- 29 = The DDE transaction failed.
- 30 = The DDE transaction could not be completed because other DDE transactions
                        were
- 31 = There is no application associated with the extension given for the
                        filename.
- 32 = The specified dynamic link library was not found.


**Err** 

Optional. Determines what the runtime will do if an error occurs while executing this command. The following rules apply: 

- **Err** (Indicator Variable) - The specified Indicator is set if an error occurred.
- **Err** (*EXTENDED) - A program status flag is set whose status can be checked using the <a href="ERROR_Function.html) built-in function.
- If the **Err** keyword is not given and an error occurs, a runtime exception will be thrown.


**Type** 

Optional. Can be any of the "*" Types (*CHAR, *BINARY, etc.) or it can be the name of a field already defined in the program, a string literal or a library object, as described below. See [Type Parameter](Type_Parameter.html) for further information. 

- Name is the name of the variable already defined.
- A string literal, which defines an *OBJECT variable of a particular type. The string literal must represent: 
<ul>
                            <li type="square">

a valid program id registered on your system at compile time
- a valid class id registered on your system at compile time.
- a valid interface name registered on your system at compile time.

</li>
                    <li>

A name of the form Library.Object, where Library is the name of one of the libraries selected in the new up and coming object libraries dialog, and Object is valid object name within that library. 
</li>
                </ul>

If a **Type** parameter is not given, the **Len** parameter is required. In this case, *CHAR is assumed if there is one integer, and *ZONED is assumed if there are two integers.


**Len** 

Optional. Defines the length of the field. If **Len** is decimal (3,1) *ZONED is assigned as the default. If **Len** is character (3), *CHAR is assigned as the default. 

Depending upon the **Type** specified, the **Len** parameter may be required. For instance, Types of *BINARY, *CHAR, *PACKED, *ZONED, *DECIMAL, *FLOAT, *INTEGER will require a **Len** . A compiler message will display if the **Len** parameter is needed.


**Operation** 

Optional. Specifies what type of operation is to be performed on the file. You can either open the file (*OPEN), print the file, (*PRINT) or explore the folder (*EXPLORE) specified by CmdLine. 

- *OPEN opens the file specified by **CmdLine** . The file can be an executable file or a document file. The file can be a folder to open. *OPEN is the default.
- *PRINT prints the file specified by **CmdLine** . The file should be a document file. If the file is an executable file, *PRINT merely opens the file, as if *OPEN had been specified.
- *EXPLORE explores the folder specified by **CmdLine** .


**Directory** 

Optional. Contains the string that specifies the default directory. For example, *...\Program Files\My Programs\Customer.EXE*


**Wait** 

Optional. Determines whether the program will wait for the launched application to end before continuing execution. The **Wait** parameter can be an expression that returns an Indicator, in addition to the constants *YES and *NO.


**ExitCode** 

Optional. Determines the variable that will receive the exit code of the launched application after waiting for it to finish. To be able to use **ExitCode** , **Wait** must not be the constant *NO. If **Wait** is an expression that evaluates to *NO, the variable in **ExitCode** will receive the value 0. If an error occurs when launching the application, the **ExitCode** variable receives 0. Verify that the **Err** indicator is *OFF before using the value returned in **ExitCode** .


### Remarks
A good way to test your **OSEXEC** command is to confirm that it can be run from the **Windows Start Menu "Run"** command. You can do anything with **OSEXEC** that you can do from the Run command line. 

The **OSEXEC** command can execute a file that has been ***associated*** with an application. For example, if the execute file is a Word document, Word will be initiated. The advantage is that if Word is already active, then the file comes up much faster. See your Windows documentation for more information on associating files with an application. 

When passing parameters to an .EXE from the command line, the following rules apply: 

- Arguments are delimited by white space, which is either a space or a tab.
- The caret character (^) is not recognized as an escape character or delimiter. The character is handled completely by the command-line parser in the operating system before being passed to the program.
- A string surrounded by double quotation marks ("string") is interpreted as a single parameter (argument), regardless of white space contained within. A quoted string can be embedded in a parameter.
- A double quotation mark preceded by a backslash (\") is interpreted as a literal double quotation mark character (").
- Backslashes are interpreted literally, unless they immediately precede a double quotation mark.
- If an even number of backslashes is followed by a double quotation mark, one backslash is placed in the parameter for every pair of backslashes, and the double quotation mark is interpreted as a string delimiter.
- If an odd number of backslashes is followed by a double quotation mark, one backslash is placed in the parameter for every pair of backslashes, and the double quotation mark is "escaped" by the remaining backslash, causing a literal double quotation mark (") to be placed in the parameter.


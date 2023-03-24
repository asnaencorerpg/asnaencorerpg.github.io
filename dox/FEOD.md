---
title: FEOD

Id: FEOD
TocParent: aerLrfOpCodesMain
TocOrder: 1060


---

Causes a file to start printing, mainly print files.

```
 **FEOD
File** (file name)
Err (Indicator Variable | *EXTENDED)
Reset (Indicator Expression | <u>*NO</u> | *YES)
```

### Parts

**File** 

Required. Specifies the name of the file to print.


**Err** 

Optional. Determines what the runtime will do if an error occurs while executing this command. The following rules apply: 

- **Err** (Indicator Variable) - The specified Indicator is set if an error occurred.
- **Err** (*EXTENDED) - A program status flag is set whose status can be checked using the [%ERROR](ERROR_Function.html) built-in function.
- If the **Err** keyword is not given and an error occurs, a runtime exception will be thrown.


**Reset** 

Optional. Only valid for print files. The default value is * **NO** . If **Reset** is *YES, or has an expression that evaluates to **True** , some printer parameters may be reset properties for this file. Changing those values during **FEOD** is faster than closing and re-opening the file. One possible application is changing the number of copies of the next document sent to the printer.


With **Reset,** you may **only** change the following **PrintFile Member** properties: Copies, ReportName, Duplex and ManuscriptPath.


### Remarks
**FEOD** causes a document to start printing by first flushing the current page, then the document starts printing immediately without closing unless as noted below. 

If the [PrintFile.Preview](Preview_Property.html) is "PrintPreview", the print driver commands are saved to a temporary file on the client machine. When the **FEOD** command is issued, a preview of the printed output is displayed (nothing is yet sent to the printer). While previewing, the user has the option to then send the output to the target printer. 

### See Also
[%ERROR](ERROR_Function.html)
[CLOSE](CLOSE.html)
[DCLFILECONT](DCLFILECONT.html)
[DCLPRINTFILE](DCLPRINTFILE.html)
[PrintFile Class](aerLrfPrintFileClass.html)
[PrintFile Members](aerLrfPrintFileMembers.html)
[PrintFile.Preview Property](Preview_Property.html) 

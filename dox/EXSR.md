---
title: EXSR

Id: EXSR
TocParent: aerLrfOpCodesMain
TocOrder: 1040


---

Executes a subroutine in the local program or in the main program.

```

 **EXSR
Sr**  (Subroutine Name)<br />ParmList (<u>*NONE</u> | Parameter Name List)
```

### Parts

**Sr** 

Required. Specifies the name of the subroutine. If the subroutine name specified is defined in the current program, the current program's subroutine will be called. Otherwise, if a subroutine is found in the main program, the main program's subroutine will be called.


**ParmList** 

Optional. Allows you to declare parameters by specifying the name of a parameter list. The default is *NONE. You can also define parameters as noted in the paragraph below.


### Remarks
If the subroutine has parameters (declared by using the [DCLSRPARM](DCLSRPARM.html) command after the [BEGSR](BEGSR.html) command), you **must** pass the correct number of parameters by using the [DCLPARM](DCLPARM.html) commands after the **EXSR** . See **DCLPARM** for an example of this. 

### Example

```
DoWhile *In03 = *Off
  Exfmt frmListName
  Select
    When Option = Add
 **Exsr**  AddRecord
    When Option = Delete
 **Exsr**  DeleteRecord
  Endsl
Enddo
```

### See Also
[BEGSR](BEGSR.html)
[CAB](CAB.html)
[DCLSRPARM](DCLSRPARM.html)
[DOUNTIL](DOUNTIL.html)
[DOWHILE](DOWHILE.html)
[IF](IF.html)
[WHEN](WHEN.html)
[Comparison Operators](Comparison_Operators.html) 

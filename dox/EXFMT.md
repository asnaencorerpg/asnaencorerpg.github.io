---
title: EXFMT

Id: EXFMT
TocParent: aerLrfOpCodesMain
TocOrder: 1010


---

In ECR, **EXFMT** shows the form instance as a modal dialog box. 

In Monarch, EXFMT redirects an application to a workstation format web page. 

```
EXFMT
Fmt  (Form Name)
Err (Indicator Variable | *EXTENDED)
```

### Parts

**Fmt** 

Required. In ECR, this contains the name of the form to display. In Monarch, this contains the name of the web page to be redirected to.


**Err** 

Optional. Determines what the runtime will do if an error occurs while executing this command. The following rules apply: 

- **Err** (Indicator Variable) - The specified Indicator is set if an error occurred.
- **Err** (*EXTENDED) - A program status flag is set whose status can be checked using the [%ERROR](ERROR_Function.html) built-in function.
- If the **Err** keyword is not given and an error occurs, a runtime exception will be thrown.


### Remarks
In ECR, You can use this command to display a modal Form in your application. When this command is executed, the code following it is not executed until after the Form is closed or Hidden. 

In Monarch, you can use this execute format command to redirect an application to a workstation format web page. 

### ECR Example

```
BegClass Form1 Extends(System.Windows.Forms.Form) Access(*Public)
 DclFld F2 Type( Form2 )
 BegSr EXFMTExample Access(*Private) Event(*this.btnEXFMT.Click)
   DclSrParm sender Type(*Object)
   DclSrParm e Type(System.EventArgs)
    F2 = *new Form2()    // create instance of Form2
 **Exfmt**  F2             // same as F2.ShowDialog()
 EndSr
EndClass
```

### Monarch Example

```

<span style="COLOR: blue">DclWorkStnFile</span>  MyWorkStnFile <span style="COLOR: blue">DspFile</span>("./MyWorkStnFile.aspx")<span style="COLOR: blue">ImpOpen</span>( <span style="COLOR: gray">*No</span> ) <span style="COLOR: blue">Subfile</span>( sfl,r )
<br /><span style="COLOR: blue">ExFmt</span> sftctl    // Executes the **stlctl**  format as described by **MyWorkStnFile.aspx**  file.

```

### See Also
<br /> [HIDE](HIDE.html)
[SHOW](SHOW.html)

[DclWorkStnFile](DCLWORKSTNFILE.html) 

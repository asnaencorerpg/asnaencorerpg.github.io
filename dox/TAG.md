---
title: TAG

Id: TAG
TocParent: aerLrfOpCodesMain
TocOrder: 1500


---

Declares a label that identifies the destination of a [GOTO](GOTO.html) operation.

```
TAG Name  (Label name)
```

### Parameters

**Name** 

Required. Must contain the name of the destination of a **GOTO** operation. This name must be a unique symbolic name, which is specified in the Label of a **GOTO** operation. The name can be used as a common point for multiple **GOTO** operations.


### Remarks
The declarative **TAG** operation names the label that identifies the destination of a **GOTO** operation. It can be specified anywhere within calculations, including within total calculations. 

A **GOTO** within a subroutine in the main procedure can be issued to a **TAG** within the same subroutine, detail calculations or total calculations. A **GOTO** within a subroutine in a subprocedure can be issued to a **TAG** within the same subroutine, or within the body of the subprocedure. 

The **TAG** command is **not** allowed within a TRY/CATCH block. 

### See Also
[GOTO](GOTO.html)

[LABEL](Labels.html) 

---
title: CAB

Id: CAB
TocParent: aerLrfOpCodesMain
TocOrder: 170


---

Computes the comparison expression, and if true, branches to the [TAG](TAG.html) operation or label associated with the **LABEL** parameter. Otherwise, the program continues with the next operation in the sequence. 

```
CAB
Cond  (Expression)
 Label  (Character expression)
```

### Parameters

**Cond** 

Required. The expression of the condition.


**Label** 

Required. The name of the routine to branch to.


### Remarks
The **CAB** command is **not** allowed within a TRY/CATCH block. 

### Example

```
 CAB COND( DollarsEarned <> 0 ) LABEL( OK )
      MSGBOX MSG( "Error - DollarsEarned = 0. Press OK to abort")
	MOVE Source( *ON ) Target( *INLR )
	RETURN
	TAG Name( OK )
	DIV F1( HoursWorked ) F2( DollarsEarned ) Result( DollarsPerHour ):
```

### See Also
[COMPARE](COMPARE.html)

[IF](IF.html)

[TAG](TAG.html) 

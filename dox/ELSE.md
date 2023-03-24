---
title: ELSE

Id: ELSE
TocParent: aerLrfOpCodesMain
TocOrder: 750


---

Marks the beginning of a group of statements to be executed if the condition on a prior **IF** was false. 

```

 **ELSE** 
        
```

### Remarks
If the [IF](IF.html) comparison is met, the calculations before **ELSE** are processed; otherwise, the calculations after **ELSE** are processed. 

Use the [ENDIF](ENDIF.html) operation to end an **IF** / **ELSE** block of commands. 

Conditioning indicator entries are not allowed. 

### Example

```
// If indicator 41 is On, process subroutine ProcessIfOn, else process subroutine ProcessIfOff. 

If *In41 = *On
   Exsr ProcessIfOn
  Else
   Exsr ProcessIfOff
Endif 

// If Acode is equal to A and indicator 50 is On, the expression and Write operations are processed. 

If Acode = "A" *And *In50 = *On
   AcRec = "A"
   Write RcRsn
Endif 

/* If the previous conditions were not met but Acode is equal to A, indicator 50 is off, and AcRec is equal to D,
   the following expression is processed. */ 

Else
 If Acode = "A" *And *In50 = *On *And AcRec = "D" 
   AcRec = "A" 
Endif 
```

### See Also
[ENDIF](ENDIF.html)
[IF](IF.html) 

---
title: ENDSR

Id: ENDSR
TocParent: aerLrfOpCodesMain
TocOrder: 930


---

Defines the end of a subroutine or event-handler.

```
ENDSR        
```

### Remarks
**ENDSR** must be the last statement in the subroutine. 

Conditioning indicator entries are not allowed.

The **ENDSR** causes a subroutine to branch back to the statement immediately following the [EXSR](EXSR.html) operation, unless the subroutine is an event handler, in which case control goes back to the event cycle. 

### Example

```
//Subroutine to get customer details record with **Endsr**  used to define an exit.

BegSR 
    GetDetail
    ReadRand CustMaster CustNumber NotFnd(*IN99)<br />    If *IN99<br />    CustNbr = 0<br />    CustName = ""<br />  Endif<br />EndSR 
```

### See Also
[BEGSR](BEGSR.html)

[EXSR](EXSR.html)

[HIDE](HIDE.html)

[SHOW](SHOW.html)

[UNLOAD](UNLOAD.html) 

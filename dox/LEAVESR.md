---
title: LEAVESR

Id: LEAVESR
TocParent: aerLrfOpCodesMain
TocOrder: 1180


---

**LEAVESR** transfers out of the current subroutine, property or function. 

```
 **LEAVESR** Value (value to return)
```

### Parts

**Value** 

Optional. However, the parameter is required when used with **BEGFUNC** and also when used with **BEGPROP's** BEGGET.


### Remarks
**LEAVESR** causes control to transfer out of the current procedure. 

**LEAVESR** is allowed inside of a [TRY](TRY.html)/[CATCH](CATCH.html) block. 

**LEAVESR** must be contained within the *GET routine of the [BEGPROP](BEGPROP.html)/[BEGFUNC](BEGFUNC.html) and [ENDPROP](ENDPROP.html)/[ENDFUNC](ENDFUNC.html) groups. 

Encore RPG allows you to name a control property for the **LeaveSR** *Value* parameter. However, you must not assume the default property for the control. Instead, you must specifically code the desired property. 

**Failure to specify the property can cause your application to crash.** 

The only branching commands allowed inside a TRY/CATCH block are [LEAVE](LEAVE.html), [ITERATE](ITERATE.html), and [LEAVESR](LEAVESR.html). Any other branching command (CAB, GOTO, etc.) is not allowed in this context. It is also illegal to branch out of a FINALLY clause (i.e., you cannot use any of the branching commands (ITERATE, CAB, LEAVESR, GOTO, etc) in the body of a FINALLY clause. 

If you do not code a specific property for the control, Encore RPG returns the control's IDispatch regardless of the data type of the **BEGPROP** or **BEGFUNC** . 

### Example
**Examples within BegFunc:** 

```
BegFunc myFunction type(*string)
  LeaveSR Value ( Label1.Caption )
EndFunc
```
When a BegFunc or BegProp type is *object, then you are required to omit the property. 

```
BegFunc myFunction type(*Object)
  LeaveSR Value ( Label1 )
EndFunc
```
**Example within BegProp:** 

```
BegProp Name (MyProp) event (*GET) type (*PACKED) Len (4,0) 
  Leavesr ValueSet
Endprop
```

### See Also
[BEGFUNC](BEGFUNC.html)
[BEGPROP](BEGPROP.html)
[BEGSR](BEGSR.html)
[CATCH](CATCH.html)
[ENDFUNC](ENDFUNC.html)
[ENDPROP](ENDPROP.html)
[ENDSR](ENDSR.html)
[TRY](TRY.html) 

---
title: "%ERROR Function"

Id: ERROR_Function
TocParent: Functions_overview
TocOrder: 18


---

**%ERROR** [built-in function](Functions_overview.html) returns **True** if the most recent operation with error operation extender specified resulted in an error condition. 

```
% **ERROR** 
```

### Remarks
This is the same as the error indicator being set on for the operation. Before an operation with an error operation extender begins, **%ERROR** is set to return False and remains unchanged following the operation if no error occurs. All operations that allow an error indicator can also set or reset the **%ERROR** built-in function. 

The implementation of RPGIV's **%ERROR** built-in function is that each program has its own **%ERROR** . The "program" analog in a .NET Windows application is the current thread. **%ERROR** is NOT unique per class - it can be used by shared and non-shared members. **%ERROR** is a per-thread shared flag, and is therefore thread-safe when used in multithreading. **%ERROR** is stored in thread local storage using **Thread.GetNamedDataSlot** and **Thread.SetData** (which means it cannot be quickwatched). Because all ECR .NET objects in the thread share the same **%ERROR** built-in function, use of the **Try/Catch/Throw** is advised when you need more granular error handling. 

### Example

```
CHAIN From(myfile) Key(myKey) Err(*EXTENDED)
If %Error
   .
   . // error handling here
   .
Endif
      
```

### See Also
[Built-in Function Overview](Functions_overview.html)

[IsError Property](IsErrorPropertyDbFileClass.html) 

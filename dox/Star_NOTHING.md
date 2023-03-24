---
title: "*NOTHING"

Id: Star_NOTHING
TocParent: aerLrfFigConstantsMain
TocOrder: 15


---

Setting a reference type variable - that is, an object variable to ***Nothing** means that the variable is not associated with any object. For example: 

```
Dclfld MyObject Type( *Object ) New() // instances MyObject
MyObject = *Nothing   	              // No object currently referred to.
```
When you assign * **Nothing** to an object variable, it no longer refers to any object instance. If the variable had previously referred to an instance, setting it to * **Nothing** does not terminate the instance itself. The instance is terminated and the memory and system resources associated with it are released, only after the garbage collector detects there are no active references remaining. 

### See Also
[Figurative Constants](aerLrfFigConstantsMain.html)
[Figurative Constants Rules](Fig_Constants_Rules.html) 

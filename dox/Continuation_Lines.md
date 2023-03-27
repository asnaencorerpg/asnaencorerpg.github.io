---
title: Continuation Lines

Id: Continuation_Lines
TocParent: aerLrfLangElementsMain
TocOrder: 1


---

Since the new line character is used in the Encore RPG Language as a command separator, a continuation character "+" is provided to span a command across line boundaries. The plus character must be the last non white-space character on the line and cannot be embedded in a string or comment. Attention should be given when continuing an expression. 

### Example

```
SCAN     

CmpStr (Name) CmpLen (3) 
	BaseStr (MonthTable) +
	StartPos (1) FndPos 
	(MonthIndex) +
	Fnd (*IN01)
	Month = MonthIndex -1 / 3 +
	+ 12
      
```

### See Also
[Language Elements](aerLrfLangElementsMain.html)

[Comments](Comments.html) 

---
title: "%EDITW Function"

Id: EDITW_Function
TocParent: Functions_overview
TocOrder: 15


---

<span style="FONT-WEIGHT: bold">%EDITW</span> [built-in function](Functions_overview.html) returns a character result representing the numeric value edited according to the edit word. 

```

 **%EDITW (Numeric, Editword)** 
        
```

### Parts

**Numeric, Editword** 

Required. The rules for the **Numeric** value and [Editword](ecrLrfEditWordTable.html) are identical to those for editing **numeric** values in output specifications.


### Example
If the values of mySalary is 2451.53, and myEditWd is " **$,,**Dollars Cents** ", then the edited version of mySalary * 12 is:<br /> 

```
(amount = 'The annual salary is // + %editw (mySalary * 12 , myeditwd)
```

### See Also
[Built-in Function Overview](Functions_overview.html)

[Edit Word Usage](ecrLrfEditWordTable.html) 

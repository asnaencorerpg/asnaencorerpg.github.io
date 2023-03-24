---
title: Concatenation Operators

Id: aerConConcatenationOperators
TocParent: aerConOperators
TocOrder: 2


---

Concatenation operators join multiple strings into a single string. There are two concatenation operators, **+** and **&** ; both carry out the basic concatenation operation, as shown below: 

```
DCLFLD x Type (*String) 
   x = "Con" & "caten" & "ation" // x equals "Concatenation". 
   x = "Con" + "caten" + "ation" // x equals "Concatenation".
```

These operators can also concatenate **String** variables, as in the following example: 

```
DCLFLD x Type (*String)= "abc" 
DCLFLD y Type (*String)
   x = "abc"
   y = "def"  
DCLFLD zType (*String)
   z = x & y   // z equals "abcdef".
   z = x + y   // z equals "abcdef".
```

### See Also
[+ Operator](Plus_Operator.html)
[String Manipulation](aerConManipulatingStrings.html) 

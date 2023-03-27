---
title: "%OCCUR Function"

Id: OCCUR_Function
TocParent: Functions_overview
TocOrder: 33


---

**%OCCUR** [built-in function](Functions_overview.html) sets or gets the current position of a **Multiple** **Occurrence** **Data** **Structure** . 

```

 **%OCCUR (DSN_name)** 
        
```

### Parts

**DSN_name** 

Required. Contains the name of the Data Structure.


### Remarks
When this function is evaluated for its value, it returns the current occurrence number of the specified Data Structure. This in an unsigned numeric value. When this function is specified on the left-hand side of an EVAL statement, the specified number becomes the current occurrance. This must be a non-float numeric value with zero decimal positions. See [OCCUR](OCCUR.html) operation code for more information about multi-occurrence data structures. 

### See Also
[Built-in Function Overview](Functions_overview.html)

[Multiple Occurrence Data Structures](Mult_Occur_DS.html)

[OCCUR](OCCUR.html) 

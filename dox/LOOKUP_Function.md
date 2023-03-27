---
title: "%LOOKUP Function"

Id: LOOKUP_Function
TocParent: Functions_overview
TocOrder: 28


---

**%LOOKUP** [built-in function](Functions_overview.html) returns the array index of the item in ***Array*** that matches the ** *Argument* ** ; otherwise, negative one is returned if no match is found. 

```

 **%LOOKUP   (Argument, Array** {, Start-index {, Num-elements}} **)** 
 **%LOOKUPLT (Argument, Array** {, Start-index {, Num-elements}} **)** 
 **%LOOKUPGE (Argument, Array** {, Start-index {, Num-elements}} **)** 
 **%LOOKUPGT (Argument, Array** {, Start-index {, Num-elements}} **)** 
 **%LOOKUPLE (Argument, Array** {, Start-index {, Num-elements}} **)** 
```

### Parts

**Argument, Array** 

Required. Contains the search argument and the name of the array to be searched. Both must be the same type but do not need to be the same length.


**Start-index, Num-elements** 

Optional. Non-float numerics with zero decimal positions, containing the index in which to begin the search, and the number of elements to be searched. By default, the entire ***Array*** is searched.


### Remarks
If no match is found, -1 is returned. Unlike green-screen RPG"s one-based %LOOKUP, ECR"s %LOOKUP is zero-based. 

The search starts at index ***Start-index*** and continues for ** *Num-elements* ** . The function returns the array index of the item in ***Array*** that matches ***Argument*** as follows: 

- %LOOKUP - for an exact match.
- %LOOKUPLT - for the value that is closest to,  but less than ***Argument*** 
                in value.
- %LOOKUPLE - for an exact match, or the value that is closest to, but
                is less than ***Argument*** 
                in value.
- %LOOKUPGT - for the value that is closest to, but greater than ***Argument*** 
                in value.
- %LOOKUPGE - for an exact match, or the value that is closest to, but
                greater than ***Argument***  in value.

Unlike the [LOOKUP](LOOKUP.html) op code, **%LOOKUP** only applies to arrays. To look up a value in a table, use the [%TLOOKUP](TLOOKUP_Function.html) function. 

**Note** : [%FOUND](FOUND_Function.html) and [%EQUAL](EQUAL_Function.html) are **NOT** set following a **%LOOKUP** operation. 

### See Also
[Built-in Function Overview](Functions_overview.html)

[DCLARRAY](DCLARRAY.html)

[DclAliasGroup](DCLALIASGROUP.html)

[DCLDSFLD](DCLDSFLD.html)

[LOOKUP](LOOKUP.html)

[%EQUAL](EQUAL_Function.html)

[%FOUND](FOUND_Function.html)

[%TLOOKUP](TLOOKUP_Function.html) 

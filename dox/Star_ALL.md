---
title: "*ALL/*ALL\"x..\""

Id: Star_ALL
TocParent: aerLrfFigConstantsMain
TocOrder: 0


---

The ***ALL** is a character constant that refers to **ALL** of the implicitly-opened files, objects, etc. 

*ALL can be used with the **CLOSE** , **CLEAR** and **SUBSTR** op codes; along with the % **Size** function. 

***ALL’x..’ Character/numeric fields** : Character string x . . is cyclically repeated to a length equal to the associated field. If the field is a numeric field, all characters within the string must be numeric (0 through 9). No sign or decimal point can be specified when *ALL’x..’ is used as a numeric constant. 

**Note the following:** 

- No space is allowed between *ALL and "x.."
- You cannot use *ALL’x..’ with numeric fields of float format.
- For numeric integer or unsigned fields, the value is never greater than the
                maximum value allowed for the corresponding field. For example, *ALL’95’
                represents the value 9595 if the corresponding field is a 5-digit integer
                field, since 95959 is greater than the maximum value allowed for a 5-digit
                signed integer.

Commands supporting ***ALL’x..’** : **dclArray** , **dcldsFld** , **dclFld** , **Move** , **MoveArr** , **Movel** and **Zadd** . 

### See Also
[Figurative Constants](aerLrfFigConstantsMain.html)

[Figurative Constants Rules](Fig_Constants_Rules.html)

[Data Types](aerLrfDataTypesMain.html) 

---
title: Compare Operations Rules

Id: Compare_Operations_Rules
TocParent: Comparison_Operators
TocOrder: 10


---

The compare operations test for certain conditions existing between two operands. 

Keep the following in mind when using Compare operations: 

- Numeric fields with blanks are assumed to be zeroes.
- An array name cannot be specified in a compare operation, but an array element may be specified.
- A numeric field cannot be compared to a character field.
- Numeric fields are converted to zoned decimal format if necessary, before they are compared.
- In comparing character fields, unequal length fields are aligned to their leftmost character. The shorter field is filled with blanks to equal the length of the longer field so the field lengths are equal for comparison.
- In comparing numeric fields, unequal length fields are aligned at the implied decimal point. The fields are filled with zeros to the left and/or right of the decimal point, making the field lengths and number of decimal positions equal for comparison.

### See Also
[Comparison Commands](Comparison_Commands.html)
[Expression Operators and Their Precedence](Expression_Operators_and_their_Precedence.html) 

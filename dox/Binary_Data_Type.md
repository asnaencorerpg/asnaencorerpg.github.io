---
title: "*Binary Data Type"

Id: Binary_Data_Type
TocParent: aerLrfDataTypesMain
TocOrder: 0


---

The * **Binary** data type means that the sign (positive or negative) is in the leftmost bit of the field and the numeric value is in the remaining bits of the field. 

The size of * **Binary** fields in ECR (vs. System i), is its Digits (just like * **Zoned** ). This is how it is stored and used throughout the program. Using the function % **Size** will return the "correct" size and not the "False" size (as expected on System i), as shown in the example below. 

```

  DCLFLD myBinary *Binary (8,0)
    % Size (myBinary) //returns 8  
```

Positive numbers have a zero in the sign bit; negative numbers have a one in the sign bit and are in twos complement form. A binary field can be from one to nine digits in length and can be defined with decimal positions. 

- If the length of the field is from five to nine digits, the compiler assumes a binary field length of 4 bytes.
- The default initialization value for numeric fields is **zero** .

### See Also
[Data Types](aerLrfDataTypesMain.html) 

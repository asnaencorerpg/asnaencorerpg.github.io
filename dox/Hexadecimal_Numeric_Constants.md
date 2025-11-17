---
title: Hexadecimal Numeric Constant

Id: Hexadecimal_Numeric_Constants
TocParent: aerLrfConstantsMain
TocOrder: 0


---

**Hexadecimal** **numeric constants** take the form: **H \<hex digits\>** 

where \<hex digits\> is a string of hexadecimal characters (0 to 9 and A to F) enclosed in single quotes ( // ), with a length from 1 to 16 characters.  

### Remarks

Hex constants are another way to declare integral constants. The size of the integral depends on the length of the hex string (and not on the value of the hex number): 

- If the length is from 1 to 2 digits, then the type is [\*Byte](Byte_Data_Type.html). 

- if the length is from 3 to 4 digits, the type is [\*Integer2](Integer2_data_type.html). 

- if the length is from 5 to 8 digits, the type is [\*Integer4](Integer4_Data_Type.html). 

- if the length is from 9 to 16 digits, the type is [\*Integer8](Integer8_Data_Type.html). 

<br /> 

So H"00000001" will be a number 1 with type [\*Integer4](Integer4_Data_Type.html) , while H"1" will be a number **1** with type [\*Byte](Byte_Data_Type.html) . 

### Example

```
 H"34B"    
 H"800040ef"
```

### See Also
[Hexadecimal Literal](Hexadecimal_Literal.html)

[\*Byte Data Type](Byte_Data_Type.html)

[\*Integer2 Data Type](Integer2_data_type.html)

[\*Integer4 Data Type](Integer4_Data_Type.html)

[\*Integer8 Data Type](Integer8_Data_Type.html) 

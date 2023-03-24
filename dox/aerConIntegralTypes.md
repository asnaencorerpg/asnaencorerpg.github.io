---
title: Integral Types

Id: aerConIntegralTypes
TocParent: aerConNumericDataTypes
TocOrder: 0


---

*Integral data types* are those that represent only whole numbers. If a variable always stores whole numbers rather than numbers with a fractional amount, declare it as one of these types. 

The unsigned integral type is <code>* **Byte** </code> (8-bit). If a variable contains binary data, or data of unknown nature, declare as this type. If more than eight bits of data are needed, declare the variable as an array of <code>* **Byte** </code> elements. 

Arithmetic operations are faster with integral types than with other data types. They are fastest with the <code>* **Integer** </code> type in Encore RPG. 

Since <code>* **Byte** </code> is an unsigned type with a range of 0-255, it cannot represent a negative number. If you use the unary minus ( **-** ) operator on an expression that evaluates to type <code> ***Byte** </code>, Encore RPG converts the expression to <code>* **Integer** </code> first. 

If you try to set a variable of an integral type to a number outside the range for that type, an error occurs. If you try to set it to a fraction, the number is rounded. 

Binary data stored in <code>* **Byte** </code> variables and arrays is preserved during format conversions. You should not use a <code> ***String** </code> variable for binary data, because its contents can be corrupted during conversion between ANSI and Unicode formats. Such conversion can happen automatically when Visual RPG reads or writes files, or when it calls DLLs, methods, and properties. 

### See Also
[Arrays](Array_Element.html)
[<code>*Integer</code> Data type](Integer_Data_Type.html)
[<code>*Byte</code> Data type](Byte_Data_Type.html) 

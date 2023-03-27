---
title: Variable-Length Character Fields

Id: Variable_Length_Character_and_UCS_2_Formats
TocParent: aerLrfVariablesMain
TocOrder: 55


---

Variable-length character fields have a declared maximum length and a current length that can vary while a program is running. The storage allocated for variable-length character fields is 2 bytes longer than the declared maximum length. The leftmost 2 bytes are an unsigned integer field containing the current length in characters. The actual character data starts at the third byte of the variable-length field. 

You define a variable-length character data field by using the LIKE keyword on a definition specification where the parameter is a variable-length character field. 

By default, a variable-length field is initialized to have a current length of zero. 

### Example
For examples of using variable-length fields, refer to the following topics. 

- [Using Variable-Length Fields](Using_Variable_Length_Fields.html)
- [%Len](LEN_Function.html)

### See Also
[%Len](LEN_Function.html)

[Using Variable-Length Fields](Using_Variable_Length_Fields.html) 

---
title: Using Variable Length Fields

Id: Using_Variable_Length_Fields
TocParent: aerLrfVariablesMain
TocOrder: 100


---

The length part of a variable-length field represents the current length of the field measured in characters. For character fields, this length also represents the current length in bytes. For double-byte fields (Unicode), this represents the length of the field in double bytes. For example, a unicode-2 field with a current length of 3 is 3 double-byte characters long, and 6 bytes long. 

The following sections describe how to best use variable-length fields and how the current length changes when using different operation codes. 

#### How the Length of the Field is Set:
When a variable-length field is initialized using **INZ** , the initial length is set to be the length of the initialization value. For example, if a character field of length 10 is initialized to the value "ABC", the initial length is set to 3. 

The [EVAL](EVAL.html) operation changes the length of a variable-length target. For example, if a character field of length 10 is assigned the value "XY", the length is set to 2. 

The [CLEAR](CLEAR.html) operation changes the length of a variable-length field to 0. 

The [DCLPARM](DCLPARM.html) operation sets the length of the result field to the length of the field in Factor 2, if specified. 

The recommended use for [MOVE](MOVE.html) and [MOVEL](MOVEL.html), as opposed to **EVAL** , is for hanging the value of fields that you want to be temporarily fixed in length. An example is building a report with columns whose size may vary from day to day, but whose size should be fixed for any given run of the program. 

When a field is read from a file (Input specifications), the length of a variable-length field is set to the length of the input data. 

You can set the length of a variable-length field yourself using the [%Len](LEN_Function.html) built-in function on the left-hand-side of an **EVAL** operation. 

#### How the Length of the Field is Used:
When a variable-length field is used for its value, its current length is used. 

#### Why You Should Use Variable-Length Fields:
Using variable-length fields for temporary variables can improve the performance of string operations. In addition, it can make your code easier to read since you do not have to save the current length of the field in another variable for [%SUBST](SUBST_Function.html) or use [%TRIM](TRIM_Function.html) to ignore the extra blanks. 

If a sub-procedure is meant to handle string data of different lengths, using variable-length fields for parameters and return values of prototyped procedures can enhance both the performance and readability of your calls and your procedures. You will not need to pass any length within your sub-procedure to get the actual length of the parameter. 

### See Also
[EVAL](EVAL.html)

[CLEAR](CLEAR.html)

[DCLPARM](DCLPARM.html)

[MOVE](MOVE.html)

[MOVEL](MOVEL.html)

[%Len](LEN_Function.html)

[%SUBST](SUBST_Function.html)

[%TRIM](TRIM_Function.html) 

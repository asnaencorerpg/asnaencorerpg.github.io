---
title: "%LEN Function"

Id: LEN_Function
TocParent: Functions_overview
TocOrder: 27


---

**%Len** [built-in function](Functions_overview.html) can be used to get the length of a program defined variable or database variable defined as "[Varying](Variable_Length_Overview.html)". It can also be used to set the current length of such fields. 

**%Len** is also supported for fixed-length fields or expressions. 

```
 **%Len (Expression)**        
```

### Parts

**Expression** 

Required. The expression to which the **%Len** function will apply.


### Remarks
When used on the left-hand side of an expression, this function sets the current length of a varying field. If the set length is greater than the current length, the characters in the field between the old length and the new length are set to blanks. A varying field length can then be read and changed at run-time using %Len ( FieldName ). 

**The following are rules to follow when using %Len:** 

The maximum length you can specify is the length that was specified for that field when declaring the field ( **DCLFLD** ). (The maximum digits for all fixed demimal numbers is 18). A run-time error will occur if the maximum length is exceeded. 

1. By assigning a string of Length X - the length of the field is changed to X. 

```
// Given an externally described varying file of length 10:
   City = "Hello" msgbox %Len( City )  // This shows a msgbox with 5, the length of the field.
```
2. When increasing the length of the field from X to Y, the ( Y-X ) characters of the field are initialized to spaces. 

```
// Given an externally described varying field of length 10:
   City = "Hello"        // This from example above changes the len to 5
   %Len( City ) = 2      // City would look like "He" in Quickwatch
   %Len( City ) = 5      // Now City Should look like "He " in Quickwatch.
```
**Using %Len at Compile-Time** 

%LEN can be used to define the length of a variable based upon the defined length of another variable or data structure. The basis variable must be defined prior in the code to the use of %Len. The basis variable must also be within the same scope as the using variable. 

```
dclds MyDS
      dclDSFld    DS1      Len( 5,0 )
      dclDSFld    DS2      Len( 25 )

  dclfld     X     len( 3,2 )
  dclfld     Y     Len( %len(X),1 )    // Len( 3,1 )
  dclfld     Z     Len( %len(Y),3 )    // Len( 3,3 )
  dclfld     D     Len( %Len(MyDS))    // Len( 30 )
```

### Example

```
%Len ( FieldName ) = 30        // Sets the length of the FieldName field to 30
Length = **%Len** 	( FieldName )    // Sets the length to the length of the *FieldName*  field
```

### See Also
[Built-in Function Overview](Functions_overview.html)
[Character data type](Character_Data_Type.html)
[DCLFLD](DCLFLD.html)
[Variable Length Overview](Variable_Length_Overview.html) 

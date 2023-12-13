---
title: DCLENUMFLD

Id: DCLENUMFLD
TocParent: aerLrfOpCodesMain
TocOrder: 440


---

Declares the members of an Enumeration ([BEGENUM](BEGENUM.html)/[ENDENUM](ENDENUM.html)). 

```
DCLENUMFLD 
Name (field name)
Value (constant expression)
Attributes (Attribute 1, Attribute 2, ...)
```

### Parts

**Name** 

Required. The name of the enumeration definition.


**Value** 

Optional. If this is the first **DclEnumFld** in the Enum declaration, the default value is 0. Otherwise, the default value is the value of the previous **DlcEnumFld** plus 1.


**Attributes** 

Optional. Allows you to provide one or more attributes on the object being defined by the command. To specify more than one attribute, simply separate them with commas. 

Attributes use required or optional arguments. The required parameters are provided in positional fashion. Positional arguments are arguments that are specified in the order they are declared for the constructor of an attribute. For example, the following code calls the **Developer** constructor of an attribute with two values: BegClass MyClass Attributes(Developer("Joe Cool", 17)) 

You can also use named arguments, which are optional, to directly set the value of properties and fields of the attributes. You specify a named argument by appending ":=" to the name of the argument, followed by the value being specified. Unlike positional arguments, named arguments can be specified in any order. For example, the following code sets the value * **True** for the Reviewed property of the Developer Attribute, and **False** for the Keep field: 
<pre>
            BegClass MyClass Attributes(Developer("Joe Cool", 17, Reviewed:=*True)
          </pre>

**Note** You must use positional arguments for arguments that are used with the attribute’s constructor. Named arguments can only be used to set the values of fields and properties of attribute classes.


### Remarks
Enums are used to describe enumeration constants. Their only members are **DclEnumFld** fields. 

### Example

```
BegEnum myEnum basetype(*byte) 
 **DclEnumFld**  q4 value(4) //<--- the default value is 0
 **DclEnumFld**  q5 	   // <--- this will be 5, which is 1 plus the previous one
EndEnum			
```

### See Also
[BEGENUM](BEGENUM.html)

[ENDENUM](ENDENUM.html)

[Enumeration Definition](ecrConEnumerationsOverview.html) 

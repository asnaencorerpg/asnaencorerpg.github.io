---
title: Assignment Operation Codes

Id: aerConAssignmentOpCodes
TocParent: aerConOpCodes
TocOrder: 1


---

Assignment operation code or commands carry out assignment operations. Simple assignment operations consist of taking the value on the right side of the operator and assigning it to the variable on the left, as in this example: 

```
x = 42
```

Here, the variable <code class="ce">x``` is assigned the literal value ```42```. 

The value on the right side of the operator can be any literal, variable, expression, or function call that returns a value, as in this example: 

```
x = y + z + MyFunction(3)
```

Here, the value represented by ```y``` is added to the value represented by ```z```, which is added to the value returned by the call to ```MyFunction(3)```. The total value of this expression is then assigned to the variable ```x```. 

The assignment operator can also assign values to **String** variables and **String** expressions, as in this example: 

```
Name(x) Type (*CHAR) Len (10)
x = "String variable assignment"
x = "Con" & "cat" & "enation" // x equals "Concatenation".
```

The values of **Boolean** variables can be assigned as well, using either a **Boolean** literal or a **Boolean** expression as the right argument: 

```
DCLFLD x Type (*Boolean)
x = True
x = 45 > 1003 // x equals *False.
x = 45 > 1003 Or 45 > 17 // x equals *True.
```

The argument on the left side of the operator can be any valid variable or property. The following example demonstrates setting the value of the text property of a text box: 

```
MyTextBox.Text = "This " & "is a" & "String" 
   // MyTextBox.Text = "This is a string".
```

Other assignment operation code or commands first perform an operation on an argument before assigning it to another argument. The following example illustrates one of these operators, ```+=```, which increments the value of the variable on the left side of the operator by the value of the expression on the right: 

```
x += 1
```

In this example, 1 is added to the value of <code class="ce">x```, and that new value is then assigned to <code class="ce">x```. It is a shorthand equivalent of the following operation code or command: 

```
x = x + 1
```

A variety of compound assignment operations can be performed using operators of this type. If the value of the variable on the left side of the operator has not been set, it is treated as zero. For a list of these operators and more information about them, see in the Encore RPG Language Reference. 

Lastly, the concatenation assignment operator is useful for adding a string to the end of already existing strings, as illustrated in this example: 

```
DCLFLD x Type (*String) = ("My ")
x &= ("String"    ') x = ("My String").
```

If the variable on the left side of the concatenation assignment operator has not been assigned a value, it is treated as an empty string (```""```). 

### See Also
[Operation Code Overview](OpCodesOverview.html)

[Declaration Operation Codes](DeclarationOpCodes.html)

[Executable Operation Codes](ExecutableOpCodes.html) 

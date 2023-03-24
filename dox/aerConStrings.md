---
title: Strings

Id: aerConStrings
TocParent: aerConLanguageConceptsMain
TocOrder: 25


---

The ```* **String** ``` data type represents a series of characters (each representing in turn an instance of the ``` ***Char** ``` data type). An instance of a string can be assigned to a literal value that represents a series of characters. For example: 

```
DclFld MyString Type (*String)
MyString = "This is an example of the String data type"
```

A ***String** variable can also accept any expression that evaluates to a string. Examples are shown below: 

```
DclFld String1 Type (*String)
DclFld String2 Type (*String)
String1 = "one, two, three, four, five"
String2 = OneString.Substring(5,3)  // Evaluates to "two".
String1 = "1"
String2 = OneString & "1"  // Evaluates to "11".
```

Any literal that is assigned to a ***String** variable must be enclosed by quotation marks (""). Naturally, this makes creating a literal that contains quotation marks somewhat problematic. For example, the following code returns a compiler error: 

```
DclFld myString
	Type (*String) myString = "Look at this example!"  // This causes an error.
```

This code returns a compiler error because the compiler terminates the string after the second quotation mark, leaving the rest of the string hanging. To have a quotation mark represented in a string literal, you must represent it as two quotation marks. The following example demonstrates the correct way to include a quotation mark in a string: 

```
DclFld myString Type (*String) // The value of myString is: "Look at
this example!" myString = """Look at this example!"""
```

In the above example, the two quotation marks preceding the word ```"Look"``` exist in the string as a single quotation mark. The three quotation marks at the end of the line represent a quotation mark in the string and the string termination character. 

A string can be thought of as a series of ``` ***Char** ``` instances, and the ``` ***String** ``` type has built-in functions that allow you to perform many manipulations on a string that resemble the manipulations allowed by arrays. 

### The Immutability of Strings
A string is *immutable* , which means its value cannot be changed once it has been created. How, then, does the following example make any sense? 

```
DclFld myString Type (*String) = "This string is immutable"
myString = "Or is it?"
```

In the above example, it appears that a string is created, given a value, and then has that value changed. This appears to contradict the opening statement that strings are immutable. What is actually happening is that in the first line, an instance of **String** is created and given the value "This string is immutable". In the second line of the example, that *instance* is destroyed and a new instance is created and given the value "Or is it?". The only thing that doesn't change is the name of the variable. 

Unlike other intrinsic data types, ```* **String** ``` is a reference type. When a variable of reference type is passed as an argument to a function or subroutine, a reference to the memory address where the data is stored is passed instead of the actual value of the string. So in the previous example, the name of the variable remains the same, but it points to a new and different instance of the ``` **String** ``` class, which holds the new value. 

### See Also
[```*Char``` Data type](Character_Data_Type.html)
[Manipulating Strings](aerConManipulatingStrings.html)
[Language Concepts Main Topics](aerConLanguageConceptsMain.html) 

---
title: Manipulating Strings

Id: aerConManipulatingStrings
TocParent: aerConStrings
TocOrder: 0


---

The [Strings](https://msdn.microsoft.com/en-us/library/System.String(v=vs.90).aspx">String</a> class of the .NET framework provides many built-in methods to facilitate the comparison and manipulation of strings. It is now a trivial matter to get data about a string, or to create new strings by manipulating current strings. 

### Types of String Manipulation Methods
In this section you will read about several different ways to analyze and manipulate your strings. Some of the methods are part of the Encore RPG language, and others are inherent in the <a href="https://msdn.microsoft.com/en-us/library/System.String(v=vs.90).aspx">.NET String</a> class. 

Encore RPG methods are used as inherent functions of the language. They may be used without qualification in your code. The following example shows typical use of a Encore RPG string-manipulation command: 

```
DclFld a string  Type(*String)
  Inz("SomeString") DclFld bString Type(*String)
```

You can also manipulate strings with the methods of the <a href="https://msdn.microsoft.com/en-us/library/System.String(v=vs.90).aspx">String</a> class. 

There are two types of methods in ```String```: *shared* methods and *instance* methods. 

a shared method is a method that stems from the **String** class itself and does not require an instance of that class to work. These methods can be qualified with the name of the class ( **String** ) rather than with an instance of the **String** class. For example: 

```
DclFld a string Type (*String)
  bString = String.Copy("a literal string")
```

In the preceding example, the ```String.Copy``` method is a static method, which acts upon an expression it is given and assigns the resulting value to <code class="ce"> bString ```. 

Instance methods, by contrast, stem from a particular instance of ```String``` and must be qualified with the instance name. For example: 

```
DclFld aString Type(*String) Inz("A
  String") DclFld bString Type(*String)
  bString = aString.SubString(2,6) // bString = "String"
```

In this example, the ```SubString``` method is a method of the instance of ```String``` (that is, <code class="ce">aString```). It performs an operation on <code class="ce">aString``` and assigns that value to <code class="ce">bString```. 

### Nothing and Strings
The Encore RPG runtime and the .NET Framework evaluate ```*Nothing``` differently when it comes to strings. Consider the following example: 

```
DclFld MyString Type (*String) Inz("This is my string")
  DclFld stringLength As Integer
    // Explicitly set the string to Nothing.
    MyString = Nothing
    // stringLength = 0
    stringLength = Len(MyString)
    // This line, however, causes an exception to be thrown.
    stringLength = MyString.Length
```

An un-instanced string is evaluated as **Nothing** , and an empty string is evaluated as *Blanks or "". 

### Comparing Strings
You can compare two strings by using the <a href="https://msdn.microsoft.com/en-us/library/system.string.compare(v=vs.90).aspx">String.Compare</a> method. This is a static, overloaded method of the base string class. In its most common form, this method can be used to directly compare two strings based on their alphabetical sort order. The following example illustrates how this method is used: 

```
DclFld myString Type(*String)
  Inz("Alphabetical") DclFld secondString Type *String) Inz("Order")
DclFld result As Integer
  result = String.Compare (myString, secondString)
```

This method returns an integer that indicates the relationship between the two compared strings based on the sorting order. A positive value for the result indicates that the first string is greater than the second string. A negative result indicates the first string is smaller, and zero indicates equality between the strings. Any string, including an empty string, evaluates to greater than a null reference. 

Additional overloads of the ```String.Compare``` method allow you to indicate whether or not to take case or culture formatting into account, and to compare substrings within the supplied strings. For more information on how to compare strings, see <a href="https://msdn.microsoft.com/en-us/library/system.string.compare(v=vs.90).aspx">String.Compare</a> method. 

### Searching for Strings Within Your Strings
There are times when it is useful to have data about the characters in your string and the positions of those characters within your string. A string can be thought of as an array of characters ( **Char** instances); you can retrieve a particular character by referencing the index of that character through the **Chars** property. For example: 

```
DclFld myString Type(*String)
  Inz("ABCDE") DclFld myChar Type(*Char)
  myChar = myString.Chars(3) // myChar = "D"
```

You can use the <a href="https://msdn.microsoft.com/en-us/library/system.string.indexof(v=vs.90).aspx">String.IndexOf</a> method to return the index where a particular character is encountered, as in the following example: 

```
DclFld myString Type(*String) <br />    myString ="ABCDE" <br />DclFld myInteger Type(*Integer)<br />    myInteger = myString.IndexOf("D) // myInteger = 3
```

In the previous example, the ```IndexOf``` method of <code class="ce">myString``` was used to return the index corresponding to the first instance of the character "C" in the string. ```IndexOf``` is an overloaded method, and the other overloads provide methods to search for any of a set of characters, or to search for a string within your string, among others. The Encore RPG command ```InStr``` also allows you to perform similar functions. 

### Creating New Strings from Old
When using strings, you may want to modify your strings and create new ones. You may want to do something as simple as convert the entire string to uppercase, or trim off trailing spaces; or you may want to do something more complex, such as extracting a substring from your string. The ```System.String``` class provides a wide range of options for modifying, manipulating, and making new strings out of your old ones. 

To combine multiple strings, you can use the concatenation operators ( **&** or **+** ). You can also use the **String.Concat** Method to concatenate a series of strings or strings contained in objects. An example of the **String.Concat** method follows: 

```
DclFld a string Type(*String)
  Inz("A") DclFld bString Type(*String) Inz("B") DclFld
  cString Type(*String) Inz("C") DclFld dString Type(*String)
  Inz("D") DclFld myString Type(*String)
  // myString = "ABCD"
  myString = String.Concat(a string, bString, cString, dString) 
```

You can convert your strings to all uppercase or all lowercase strings using either the Encore RPG functions ```UCase``` and ```LCase``` or the **String.ToUpper** Method and **String.ToLower** Method methods. An example is shown below: 

```
DclFld myString Type(*String) Inz("UpPeR oR LoWeR cAsE") DclFld newString Type(*String)
  // newString = "UPPER OR LOWER CASE"
  newString = UCase(myString)
  // newString = "upper or lower case"
  newString = LCase(myString)
  // newString = "UPPER OR LOWER CASE"
  newString = myString.ToUpper
  // newString = "upper or lower case"
  newString = myString.ToLower
```

The ```<a href="https://msdn.microsoft.com/en-us/library/system.string.format(v=vs.90).aspx">String.Format</a>``` method and the Visual Basic ```<a href="https://msdn.microsoft.com/en-us/library/59bz1f0h%28v=vs.90%29.aspx">Format</a>``` command can generate a new string by applying formatting to a given string. For information on these commands, see ```<a href="https://msdn.microsoft.com/en-us/library/59bz1f0h%28v=vs.90%29.aspx">Format Function</a>``` or ```<a href="https://msdn.microsoft.com/en-us/library/system.string.format(v=vs.90).aspx">String.Format</a>``` Method. 

The ```String.Trim``` functions and related functions also allow you to remove instances of a specific character from the ends of your string. The following example trims all leading and trailing instances of the "#" character: 

```
DclFld myString Type(*String) Inz("#####Remove
  those!######") DclFld oneString Type(*String)
  OneString = myString.Trim("#")
```

You can also add leading or trailing characters by using the ```<a href="https://msdn.microsoft.com/en-us/library/system.string.padleft(v=vs.90).aspx">String.PadLeft</a>``` Method or the ```<a href="https://msdn.microsoft.com/en-us/library/system.string.padright(v=vs.90).aspx">String.PadRight</a>``` Method. 

If you have excess characters within the body of your string, you can excise them by using the ```String.Remove``` Method, or you can replace them with another character using the ```<a href="https://msdn.microsoft.com/en-us/library/system.string.replace(v=vs.90).aspx">String.Replace</a>``` Method. For example: 

```
 DclFld a string Type(*String) Inz("This is
  My Str@o@o@ing") DclFld myString
  Type(*String) DclFld anotherString Type(*String)
  // myString = "This is My String"
  myString = a string.Remove(14, 5)
  // anotherString = "This is Another String"
  anotherString = myString.Replace("my", "Another")
```

You can use the ```<a href="https://msdn.microsoft.com/en-us/library/system.string.replace(v=vs.90).aspx">String.Replace</a>``` method to replace either individual characters or strings of characters. The Encore RPG Mid Statement can also be used to replace an interior string with another string. 

You can also use the ```<a href="https://msdn.microsoft.com/en-us/library/system.string.insert(v=vs.90).aspx">String.Insert</a>``` Method to insert a string within another string, as in the following example: 

```
DclFld a string Type(*String) Inz("This is My
  Stng") DclFld myString Type(*String)
  // Results in a value of "This is My String".
  myString = a string.Insert(13, "ri")
```

The first parameter that the ```<a href="https://msdn.microsoft.com/en-us/library/system.string.insert(v=vs.90).aspx">String.Insert</a>``` method takes is the index of the character the string is to be inserted after, and the second parameter is the string to be inserted. 

You can concatenate an array of strings together with a separator string by using the ```<a href="https://msdn.microsoft.com/en-us/library/system.string.join(v=vs.90).aspx">String.Join</a>``` Method. Here is an example: 

```
 DclFld shoppingItem(2)
  Type(*String) DclFld shoppingList Type(*String)
  shoppingItem(0) = "milk"
  shoppingItem(1) = "Eggs"
  shoppingItem(2) = "Bread"
  shoppingList = String.Join(",", shoppingItem)
```

The value of <code class="ce">shoppingList``` after running this code is "milk,Eggs,Bread". Note that if your array has empty members,the method still adds a separator string between all the empty instances in your array. 

You can also create an array of string from a single string by using the ```<a href="https://msdn.microsoft.com/en-us/library/system.string.split(v=vs.90).aspx">String.Split</a>``` Method. The following example demonstrates the reverse of the previous example: it takes a shopping list and turns it into an array of shopping items. The separator in this case is an array of characters. 

```
DclFld shoppingList Type (*String) Inz("milk,Eggs,Bread")
<span style="FONT-SIZE: 9pt">   DclArray shoppingItem Type( *String ) Rank( 1 )</span><span style="FONT-SIZE: 9pt">shoppingItem = shoppingList.Split( ",".ToCharArray() ) </span>
```

Substrings of your string can also be generated using the ```<a href="https://msdn.microsoft.com/en-us/library/system.string.substring(v=vs.90).aspx">String.Substring</a>``` Method. This method takes two arguments:<br /> the character index where the substring is to start, and the length of the substring. The ```<a href="https://msdn.microsoft.com/en-us/library/system.string.substring(v=vs.90).aspx">String.Substring</a>``` method operates much like the **Mid** function. An example is shown below: 

```
DclFld a string Type (*String)
   a string = "Left Center Right"
DclFld subString Type (*String)
   // subString = "Center"
   subString = a string.SubString(5,6) 
```

### See Also
<a href="aerConStrings.html) 

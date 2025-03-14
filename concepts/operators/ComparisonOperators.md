---
title: Comparison Operators

Id: aerConComparisonOperators
TocParent: aerConOperators
TocOrder: 1


---

 Comparison operators compare two expressions and return a ```*Boolean``` value that represents the result of the comparison. There are operators for comparing numeric values, operators for comparing strings, and operators for comparing objects. All three types of operators are discussed below. 

### Comparing Numeric Values
Numeric values are compared using six numeric comparison operators. The following table lists the operators and gives an example of the condition tested by the operator. 

<table class="dtTABLE" id="Table2" cellspacing="0" width="85%">
                <tr valign="top">
                    <th colspan="1" rowspan="1" style="width: 19%">
                        Operator
                    </th>
                    <th colspan="1" rowspan="1" width="34%">
                        Condition tested
                    </th>
                    <th colspan="1" rowspan="1" style="width: 28%">
                        Examples
                    </th>
                </tr>
                <tr valign="top">
                    <td colspan="1" rowspan="1" style="height: 101px; width: 19%">
                        ```=``` (Equality)
                    </td>
                    <td colspan="1" rowspan="1" width="34%" style="height: 101px">Is the value represented by the first expression equal to the value represented by the second?</td>
                    <td colspan="1" rowspan="1" style="height: 101px; width: 28%">
                        <pre class="prettyprint">59 = 72  // False
59 = 59  // True
59 = 8 // False</pre>
                    </td>
                </tr>
                <tr valign="top">
                    <td colspan="1" rowspan="1" style="width: 19%">
                        ```<>``` (Inequality)
                    </td>
                    <td colspan="1" rowspan="1" width="34%">Is the value represented by the first expression not equal to the value represented by the second?</td>
                    <td colspan="1" rowspan="1" style="width: 28%">
                        <pre class="prettyprint">59 <> 72  // True
</pre>
                        <pre class="prettyprint">59 <> 59  // False
59 <> 8 // True</pre>
                    </td>
                </tr>
                <tr valign="top">
                    <td colspan="1" rowspan="1" style="width: 19%">
                        ```<``` (Less than)
                    </td>
                    <td colspan="1" rowspan="1" width="34%">
                        Is the value represented by the first expression less than
                        the value represented by the second?
                    </td>
                    <td colspan="1" rowspan="1" style="width: 28%">
                        <pre class="prettyprint">59 < 72  // True
</pre>
                        <pre class="prettyprint">59 < 59  // False 
59 < 8 // False</pre>
                    </td>
                </tr>
                <tr valign="top">
                    <td colspan="1" rowspan="1" style="width: 19%">
                        ```>``` (Greater than)
                    </td>
                    <td colspan="1" rowspan="1" width="34%">Is the value represented by the first expression greater than the value represented by the second?</td>
                    <td colspan="1" rowspan="1" style="width: 28%">
                        <pre class="prettyprint">59 > 72  // False
</pre>
                        <pre class="prettyprint">59 > 59  // False
59 > 8 // True</pre>
                    </td>
                </tr>
                <tr valign="top">
                    <td colspan="1" rowspan="1" style="width: 19%">
                        ```<=``` (Less than or equal to)
                    </td>
                    <td colspan="1" rowspan="1" width="34%">Is the value represented by the first expression less than or equal to the value represented by the second?</td>
                    <td colspan="1" rowspan="1" style="width: 28%">
                        <pre class="prettyprint">59 <= 72  // True
</pre>
                        <pre class="prettyprint">59 <= 59  // True
59 <= 8 // False</pre>
                    </td>
                </tr>
                <tr valign="top">
                    <td colspan="1" rowspan="1" style="width: 19%">
                        ```>=``` (Greater than or equal to)
                    </td>
                    <td colspan="1" rowspan="1" width="34%">Is the value represented by the first expression greater than or equal to the value represented by the second?</td>
                    <td colspan="1" rowspan="1" style="width: 28%">
                        <pre class="prettyprint">59 >= 72  // False
</pre>
                        <pre class="prettyprint">59 >= 59  // True
59 >= 8 // True</pre>
                    </td>
                </tr>
</table>

### Comparing Strings
Strings can be compared using the ```Like``` operator as well as using the numeric comparison operators. The ```Like``` operator allows you to specify a pattern; the string is then compared against the pattern, and if it matches, the result is ```True```. Otherwise, the result is ```False```. The numeric operators allow you to compare **String** values based on their sort order, as in this example: 

```
"73" < "9"    // This result is True.
```

The result is ```True``` because the first character in the first string sorts before the first character in the second string. If the first characters were equal, the comparison would continue to the next character in both strings, and so on. Equality of strings can also be tested using the equality operator, as in this example: 

```
"101" = "101"      // This result is True.
```

In this example, the two strings are directly compared, and, because they are equal, ```True``` is returned. 

If one string is a prefix of another, such as "ab" and "aba", the longer string sorts after the shorter. Thus the following expression is true: 

```"aba" > "ab"``` 

The sort order will be based on either a binary comparison or a textual comparison depending on the Option Compare setting. 

### Comparing Objects
In this example, ```x Is y``` evaluates to ```True```, because both variables refer to the same instance. Contrast this result with the following example: 

```
DclFld x New
MyClass() DclFld y New MyClass()
If x Is y then
// Insert code to continue program execution.
```

In this example, ```x Is y``` evaluates to ```False```, because although the variables are of the same type, they refer to different instances of that type. 

You can test whether an object is of a particular type with the ```*TypeOf...*Is``` operator. The syntax is 

```
 *TypeOf <object expression> *Is <TypeName>
```

When ```TypeName``` specifies an interface type then the ```TypeOf ... Is``` operator returns true if the object implements the interface type. When the ```TypeName``` is a class type then the operator returns true if the object is an instance of the specified class or is an instance of a class that derives from the specified class. For example: 

```
DclFld x
New (System.Windows.Forms.Form.Button) x = New Button()
   // Insert code to continue program execution.
```

Since the type of <code class="ce">x``` is <code class="ce">Button```, and <code class="ce">Button``` inherits from <code class="ce">Control```, the *```TypeOf x Is Control``` expression evaluates to ```True```. 

### See Also
[Value Comparisons](/concepts/expressions/ValueComparisons.html)

[Operators](/concepts/operators/Operators.html) 

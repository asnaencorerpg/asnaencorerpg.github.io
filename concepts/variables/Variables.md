---
title: Variables

Id: aerConVariables
TocParent: aerConLanguageConceptsMain
TocOrder: 35


---

When performing calculations with Encore RPG, you often need to store values temporarily. For example, you might want to calculate several values, compare them, and perform different operations on them, depending on the result of the comparison. You need to retain the values if you want to compare them, but you don't need to store them in a property. 

Encore RPG, like most programming languages, uses variables for storing values. A *variable* has a name (the word you use to refer to the value the variable contains) and a Data type (which determines the kind of data the variable can store). A variable can represent an array if it needs to store an indexed set of closely related data items. 

You use assignment statements to perform calculations and assign the result to a variable, as shown in the following code: 

```
UnitsSold = 10             // The value 10 is assigned to the variable.
UnitsSold = UnitsSold + 1  // The variable is incremented.
```

            <blockquote>
 **Note &#8212;**  The equal sign
                (```=```) in this example is an assignment operator, not an equality operator.
                The value is being assigned to the variable Units ```Sold```.
            </blockquote>

### In This Section

[Variable Declaration](VariableDeclaration.html)

Describes how to declare a variable to tell the program about it in advance.


[Object Variables](ObjectVariables.html)

Describes how to use variables to refer to objects.


### Related Sections

[Arrays](/concepts/arrays/intro.html)

Describes arrays, and how to declare and use them.


[Declared Elements](/concepts/declared-elements/DeclaredElements.html)

Discusses programming elements that are defined in declaration statements.


### See Also
[Language Concepts](/concepts/LanguageConceptsMain.html) 

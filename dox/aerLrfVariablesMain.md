---
title: Variables

Id: aerLrfVariablesMain
TocParent: aerLrfLangRefMain
TocOrder: 60


---

### In This Section
When performing calculations with Encore RPG, you often need to store values temporarily. For example, you might want to calculate several values, compare them, and perform different operations on them, depending on the result of the comparison. You need to retain the values if you want to compare them, but you don't need to store them in a property. 

Encore RPG, like most programming languages, uses variables for storing values. A *variable* has a name (the word you use to refer to the value the variable contains) and a data type (which determines the kind of data the variable can store). A variable can represent an array if it needs to store an indexed set of closely related data items. 

You use assignment statements to perform calculations and assign the result to a variable, as shown in the following code: 

```
UnitsSold = 10             // The value 10 is assigned to the variable.
UnitsSold = UnitsSold + 1  // The variable is incremented.
```

 **Note &#8211;**   The equal sign ( **=** ) in this example is an assignment operator,
                not an equality operator. The value is being assigned to the variable Units <code>Sold</code>.

### See Also

[Array Element](Array_Element.html)

[
                    Character
                    Expression
                ](Character_Expression.html)

[Global Variable](Variable_Scoping.html)

[Numeric Variable](Numeric_Variable.html)

[Variable Names](Variable_Names.html)

### Related Sections
[Encore RPG Language Reference](aerLrfLangRefMain.html) 

Provides a reference of the Encore RPG language.



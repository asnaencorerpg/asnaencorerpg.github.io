---
title: Names

Id: Lexical_Element_Names
TocParent: aerLrfLangElementsMain
TocOrder: 6


---

When you are writing your Encore RPG code, you name many elements, subroutines, variables, forms, controls, labels and so on. The **names** that you declare in your code must follow the following set of rules: 

- **Names** must start with an alphabetic character ( **A-Z** , **a-z** ) or the character **$** , **@** , or **#** .

- Subsequent characters in a name can be alphabetic ( **A-Z** , **a-z** ), numeric ( **0-9** ) or the character **$** , **@** , **#** , **_** (underscore), ñ, €, £, and ¥.
- There is no limit to the length of the name.

<br /> **For Example:** 

```
CUSNAM
 CustomerName
 Total$
 #ofInvoices      

```
The Encore RPG Language is case insensitive, that is, any lower case alphabetic characters are automatically turned to upper case by the compiler, unless it is seen inside a character literal. 

Since Encore RPG has no restrictions on the length of a name, more descriptive, readable names can be chosen. 

<br /> **For Example:** 

PRTNUM vs. PartNumber 

Taking advantage of this can greatly increase the readability and thus the maintainability of your programs. 

### See Also
[Language Elements](ecrLrfLangElementsMain.html)
        <br />
        [Reserved Names](Reserved_Names.html)
        <br />
        [Special Values](ecrLrfSpecialValuesMain.html)


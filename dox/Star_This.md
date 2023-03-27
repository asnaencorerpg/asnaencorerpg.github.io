---
title: "*This"

Id: Star_This
TocParent: aerLrfFigConstantsMain
TocOrder: 25


---

* **This** is a variable that refers to the current object, or form that your program is currently executing in. 

* **This** allows you to access the currently executing forms properties and methods or run any command that requires a form variable ( **SHOW** , **HIDE** , **UNLOAD** , etc.) without having to ensure that a form variable is declared and set to the desired form. 

** **This** is the equivalent of the **Me** keyword that is used in other languages such as Visual Basic and C#. Using *This is particularly useful for passing information about the currently executing instance of a class or structure to a procedure in another class, structure or program.* 

### Remarks
Design-time controls (DTC's) are no longer supported. 

### Example
The current form is closed in the following example. 
<pre class="prettyprint">*This.Close()</pre>

### See Also
[Figurative Constants](aerLrfFigConstantsMain.html)

[Figurative Constants Rules](Fig_Constants_Rules.html) 

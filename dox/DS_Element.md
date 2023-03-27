---
title: Data Structure Element

Id: DS_Element
TocParent: aerLrfVariablesMain
TocOrder: 3


---

While traditional RPG allows you to access data structure elements without referring to the data structure, Encore RPG allows **data** **structure element** names to be "hidden" in the data structure, and accessed via the "." Character. 

### Remarks
If a **data structure element** is an array, or if a control's property is an array property, individual elements of these arrays can be accessed using the [ ] characters. 

### Example
MOVE "A" MyDS.Element1<br /> MyDS.Element2= 3 

You can also access the properties of a control.

MOVE *ON IOField1 **.** FontBold<br /> MOVE *OFF IOField2 **.** FontItalic 

### See Also
[Variables](ecrLrfVariablesMain.html)

[Array Elements](Array_Element.html)

[Control Properties](Control_Properties.html)

[Fields](Field.html)

[Multiple Occurrence Data Structures](Mult_Occur_DS.html)

[Encore RPG Language Reference](ecrLrfLangRefMain.html) 

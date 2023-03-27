---
title: Control Properties

Id: Control_Properties
TocParent: aerLrfLangElementsMain
TocOrder: 140


---

A program or form can refer to properties of another active form via a *form variable* . Encore RPG *automatically* declares a form variable globally with the name of the form for each form in the project. Thus, if you have a project that has 2 form programs, FORM1.vr and FORM2.vr, and the **Name** property of each form is FORM1 and FORM2 respectively, Encore RPG declares two global form variables with the names FORM1 and FORM2. 

When a form becomes active via a [SHOW](SHOW.html) operation, or by having it as the main program, its properties can be accessed and set from outside the form. This is done using the following format: 

form.Property (or) <br /> form.control.Property 

### Example
If FORM1 shows FORM2, it can also set properties in FORM2 by doing the following: 

MOVE H"000000FF" Form2.BackColor<br /> MOVE "Hello from Form1" Form2.IOField1.Text 

### See Also
[SHOW](SHOW.html)

[Array Elements](Array_Element.html)

[Data Structure Element](DS_Element.html)

[Fields](Field.html)

[Multiple Occurrence Data Structures](Mult_Occur_DS.html)

[Visual RPG Language Reference](ecrLrfLangRefMain.html) 

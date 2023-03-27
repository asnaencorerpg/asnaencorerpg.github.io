---
title: Shared Members

Id: aerTourSharedMembers
TocParent: aerTourObjectOrientedProgrammingMain
TocOrder: 5


---

Shared members are fields and properties that are shared by all instances of a class. Some programming languages refer to such items as ***static** members* . 

Shared fields and properties are useful when you have information that is part of a class, but is not specific to any one **instance** of a class. Normal fields and properties exist independently for each instance of a class. Changing the value of a field or property associated with any one instance does not affect the value of fields or properties of other instances of the class. On the other hand, when you change the value of a shared field and property associated with an instance of a class, you change the **value** associated with all instances of the class. In this way, shared fields and properties behave like global variables that can be accessed only from instances of a class. Without static fields and properties, you would need to use module-level variables to achieve the same effect. However, module-level variables can make your classes difficult to understand and maintain. Furthermore, using module-level variables in this way violates the concept of encapsulation that classes represent. 

Shared procedures are not implicitly passed instances of the class. For this reason, no unqualified references to non-shared data members are allowed in shared methods. 

### Shared Members Example
The following example creates a shared field (```Barney```) in another class (```PublicFields```), and shows how to instance, or use that shared field to demonstrate how shared members operate in code: 

```
BegClass Form1 Extends(System.Windows.Forms.Form) Access(*Public)
      DclFld button2 Type(System.Windows.Forms.Button) Access(*Private) WithEvents(*Yes)
      DclFld button1 Type(System.Windows.Forms.Button) Access(*Private) WithEvents(*Yes)

      BegSr Form1_Load Access(*Private) Event(*this.Load)
        <span style="mso-tab-count: 2" />DclSrParm sender Type(*Object
        <span style="mso-tab-count: 2" />DclSrParm e Type(System.EventArgs
      EndSr
        <span style="mso-tab-count: 1">            </span>

      BegSr button1_Click Access(*Private) Event(*this.button1.Click)
        <span style="mso-tab-count: 2" />DclSrParm sender Type(*Object)
        <span style="mso-tab-count: 2" />DclSrParm e Type(System.EventArgs)
 //Don't need to Instance the Class if the Field is Shared (*Yes) <span style="mso-tab-count: 2" />MsgBox **PublicFields**  .Barney
      EndSr
        <span style="mso-tab-count: 1">            </span>
      BegSr button2_Click Access(*Private) Event(*this.button2.Click)
        <span style="mso-tab-count: 2" />DclSrParm sender Type(*Object)
        <span style="mso-tab-count: 2" />DclSrParm e Type(System.EventArgs)
        <span style="mso-tab-count: 2" />MsgBox **PublicFields**  .Barney
 **<strong>PublicFields** </strong>.Barney = "Pence"
      EndSr
     EndClass
      _____________________________________________

 **Contents of the Class called PublicFields** 

BegClass PublicFields Access(*Public) <br />  DclFld Fred Type( *String ) Access( *Public ) Inz( "Flintstone" )<br />  DclFld Barney Type( *String ) Access( *Public ) Inz( "Rubble" ) Shared( *Yes ) <br />EndClass

```

### See Also
[Class Properties, Fields, and Methods](aerTourClassPropertiesFieldsandMethodsMain.html)

[DCLFLD](DCLFLD.html) 

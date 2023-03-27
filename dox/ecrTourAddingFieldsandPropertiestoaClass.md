---
title: Adding Fields and Properties to a Class

Id: aerTourAddingFieldsandPropertiestoaClass
TocParent: aerTourClassPropertiesFieldsandMethodsMain
TocOrder: 5


---

You can use both fields and properties to store information in an object. Although fields and properties are almost indistinguishable from a client-application perspective, they are declared differently within a class. Whereas fields are simply public variables that a class exposes, properties use **Property** procedures to control how values are set or returned. 

**To add a field to a class** 

- Declare a public variable in the class definition, as in the following code:
                <br />
```
BegClass Form1 Extends(System.Windows.Forms.Form) Access(*Pub)
    DclFld button2 Type(System.Windows.Forms.Button) Access(*Private)
EndClass
```

**To add a property to a class** 

1. Declare a local variable within the class to store the property value. This
                step is necessary because properties do not allocate any storage on their own.
                To protect their values from direct modification, variables used to store
                property values should be declared as ```*Private```.
2. Preface property declarations with modifiers, such as ```*Public``` and
                ```*Shared```, as appropriate.
3. Use ```BEGGET``` and ```BEGSET``` commands within the
                property definition ```BEGPROP```. ```Get``` property procedures are used to return
                the value of a property and are roughly equivalent to functions in syntax. They
                accept no arguments and can be used to return the value of private local
                variables declared within the class used to store the property value. ```Set```
                property procedures are used to set the value of a property; they have a
                parameter, *```NewValueName```* , with the same data type as the property itself.
                Whenever the value of the property is changed, <code class="ce">Value``` is
                passed to the ```Set```
                property procedure, where it can be validated and stored in a local variable.
4. Terminate ```BEGGET``` and ```BEGSET``` property
                procedures with ```EndGet``` and ```EndSet```
                commands as appropriate.
5. Terminate the property block with an ```ENDPROP``` command.

The following example declares a property in a class:

```
 BegClass ThisClass 
    BegProp Prop1 Type( *Integer ) len( 4 ) Access( *Public )<br />       BegGet<br />          LeaveSR 5<br />       EndGet<br />         BegSet newvalname( Myname )   C = A * B<br />          zero[1] = D<br />       EndSet<br />    EndProp <br /> EndClass
```

When you create an instance of <code class="ce">ThisClass``` and set the value of the property <code class="ce">One```, the **Set** property procedure is called and the value is passed in the <code class="ce">Value``` parameter, which is stored in a local variable named <code class="ce">Myname```. When the value of this property is retrieved, the ```Get``` property procedure is called like a function and returns the value stored in the local variable <code class="ce"> Prop1. ``` 

### See Also
[Properties and Property Procedures](ecrTourPropertiesandPropertyProcedures.html) 

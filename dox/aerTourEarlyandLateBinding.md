---
title: Early and Late Binding

Id: aerTourEarlyandLateBinding
TocParent: aerTourObjectOrientedProgrammingMain
TocOrder: 0


---

The Encore RPG compiler performs a process called *binding* when an object is assigned to an object variable. An object is ***early** bound* when it is assigned to a variable declared to be of a specific object type. Early bound objects allow the compiler to allocate memory and perform other optimizations before an application executes. 

By contrast, an object is ***late** **bound*** when it is assigned to a variable declared to be of type ```*Object```. Objects of this type can hold references to any object, but lack many of the advantages of early-bound objects. 

You should use early-bound objects whenever possible, because they allow the compiler to make important optimizations that yield more efficient applications. Early-bound objects are significantly faster than late-bound objects and make your code easier to read and maintain by stating exactly what kind of objects are being used. Early binding reduces the number and severity of run-time errors because it allows the compiler to report errors when a program is compiled. 
<blockquote class="dtBlock">
                <b class="le">Note</b>   Late binding
                can only be used to access type members that are declared as ```*Public```.
                Accessing members declared as ```*Internal``` or ```*Protected```
                results in a runtime error.
            </blockquote>

### See Also
[Object Lifetime](aerTourObjectLifetime.html)

[Object Data Type](aerConObjects.html) 

---
title: Override Modifiers

Id: aerTourOverrideModifiers
TocParent: aerTourOverridingPropertiesandMethodsMain
TocOrder: 5


---

The **```Override```** keyword for the **```BEGFUNC```** , **```BEGPROP```** , **```BEGSR```** and **```DCLEVENT```** commands control how properties and methods are overridden in derived classes. ```*NONE``` is the default, which specifies that none of the override options are available for properties and methods. The other options are ``` *MUSTOVERRIDE, *NOTOVERRIDABLE, *OVERRIDABLE ```, and ```*OVERRIDES```. 

The ```Override (** ***NOTOVERRIDABLE)``` option specifies that a property or method cannot be overridden in a derived class. You can use the ```*NOTOVERRIDABLE``` option when you do not want to allow an **overridden** method to be overridden again in a derived class. 

Properties and Methods defined with the ```Override (** ***MUSTOVERRIDE)``` option have no implementation in the base class and must be implemented in derived classes before it can be used. 

The ```Override (** ***OVERRIDABLE)``` option specifies that a property or method can be overridden in a derived class. 

The ```Override (** ***OVERRIDES)``` option specifies that a property or method overrides a member inherited from a base class. You can use the ```*NOTOVERRIDABLE``` and ```*MUSTOVERRIDE``` modifiers to control how properties and methods are overridden in derived classes. 

### See Also
[BEGFUNC](BEGFUNC.html)

[BEGPROP](BEGPROP.html)

[BEGSR](BEGSR.html)

[DCLEVENT](DCLEVENT.html)

[Overloaded Properties and Methods](ecrTourOverloadedProperties.html) 

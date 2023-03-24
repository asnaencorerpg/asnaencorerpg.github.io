---
title: Override Modifiers

Id: aerTourOverrideModifiers
TocParent: aerTourOverridingPropertiesandMethodsMain
TocOrder: 5


---

The **<code>Override</code>** keyword for the **<code>BEGFUNC</code>** , **<code>BEGPROP</code>** , **<code>BEGSR</code>** and **<code>DCLEVENT</code>** commands control how properties and methods are overridden in derived classes. <code>*NONE</code> is the default, which specifies that none of the override options are available for properties and methods. The other options are <code> *MUSTOVERRIDE, *NOTOVERRIDABLE, *OVERRIDABLE </code>, and <code>*OVERRIDES</code>. 

The <code> **Override (** ***NOTOVERRIDABLE)** </code> option specifies that a property or method cannot be overridden in a derived class. You can use the <code>*NOTOVERRIDABLE</code> option when you do not want to allow an **overridden** method to be overridden again in a derived class. 

Properties and Methods defined with the <code> **Override (** ***MUSTOVERRIDE)** </code> option have no implementation in the base class and must be implemented in derived classes before it can be used. 

The <code> **Override (** ***OVERRIDABLE)** </code> option specifies that a property or method can be overridden in a derived class. 

The <code> **Override (** ***OVERRIDES)** </code> option specifies that a property or method overrides a member inherited from a base class. You can use the <code>* **NOTOVERRIDABLE** </code> and <code>* **MUSTOVERRIDE** </code> modifiers to control how properties and methods are overridden in derived classes. 

### See Also
[BEGFUNC](BEGFUNC.html)
[BEGPROP](BEGPROP.html)
[BEGSR](BEGSR.html)
[DCLEVENT](DCLEVENT.html)
[Overloaded Properties and Methods](aerTourOverloadedProperties.html) 

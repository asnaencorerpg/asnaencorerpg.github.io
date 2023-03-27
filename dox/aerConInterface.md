---
title: Interfaces in Encore RPG

Id: aerConInterface
TocParent: aerConLanguageConceptsMain
TocOrder: 200


---

Interfaces are similar to classes, as they define a set of properties, methods, and events. But unlike classes, interfaces do not provide implementation. They are implemented by classes, and defined as separate entities from classes. 

Although interface implementations can evolve, interfaces themselves cannot be changed once published, as changes to a published interface may break existing code. If you think of an interface as a contract, it is clear that both sides of the contract have a role to play. The publisher of an interface agrees never to change that interface, and the implementer agrees to implement the interface exactly as it was designed. 

Polymorphism in components can be implemented in a variety of ways:

**Interface polymorphism** - Multiple classes may implement the same interface, and a single class may implement one or more interfaces. Interfaces are essentially definitions of how a class needs to respond. An interface describes the methods, properties, and events that a class needs to implement, and the type of parameters each member needs to receive and return, but leaves the specific implementation of these members up to the implementing class. 

**Inheritance polymorphism** - Multiple classes may inherit from a single base class. By inheriting, a class receives all of the methods, properties, and events of the base class in the same implementation as the base class. Additional members can then be implemented as needed, and base members can be overridden to provide different implementations. Note that an inherited class may also implement interfaces — the techniques are not mutually exclusive. 

**Polymorphism** through abstract classes - Abstract classes provide elements of both inheritance and interfaces. An abstract class is a class that cannot be instantiated itself; it must be inherited. Some or all members of the class might be unimplemented, and it is up to the inheriting class to provide that implementation. Members that are implemented might still be overridden, and the inheriting class can still implement additional interfaces or other functionality. 

### See Also
[BEGINTERFACE](BEGINTERFACE.html)

[ENDINTERFACE](ENDINTERFACE.html)  

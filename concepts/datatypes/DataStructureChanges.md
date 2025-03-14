---
title: Data Structure Changes


---

Data structure declarations needed a support of extracting their field definitions into a class and using that class as the basis of its field definitions. Users can write their classes in any language they wish and when that class/type is used as the basis of the field definitions of a DS, all the public fields and properties of that class/type become the fields of the Datastructure. 

**Changes in Data structures** 

When declaring a datastructure (DCLDS) as a TYPE on another DS, all the DCLDSes now generate classes. Note that a big change is now **DCLDS** are ** *Reference* ** Types and not Value types. Internally they generate either a **DSName_DS** class for a single occurrance DS or **DSName_MODS** for a multi-occurrance datastructure. 

There are certain OPCODES that data structures need to be recognized as such and not just a class name and hence a "Data structure" implements **ASNA.QSys.Runtime.IDS interface** . The interface contains the following methods and properties. 

1. Load method – Needed for the [DSLoad](/dox/DSLOAD.html) opcode.
2. Dump method – Needed for the [DSDump](/dox/DSDUMP.html) opcode.
3. Clear method – Needed for the [Clear](/dox/CLEAR.html) opcode.
4. ObjectToParm method – Needed for passing this DS as a INPUT parm on the Remote Call.
5. ParmToObject method - Needed for passing this DS as an OUTPUT parm on the Remote Call.
6. Length property – Returns the length of the DS.

If the datastructure is a Multi-occurrance DS it implements **ASNA.QSys.Runtime.IMODS** that has the following properties and methods. 

7. Occurrance – Gets and sets the current occurrance.
8. ClearAll - Calls clear for **all**  occurrances of the DS.
9. DumpAll – Dumps **all**  occurrances of the DS using ToString().
10. LoadAll – Loads **all**  occurrances of the DS from a source string.

A class that does not implement can still be used on DCLDS TYPE keyword but can not be used with those opcodes. 

### See Also
[DCLDS](/dox/DCLDS.html) 

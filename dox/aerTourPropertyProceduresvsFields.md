---
title: Property Procedures vs. fields

Id: aerTourPropertyProceduresvsFields
TocParent: aerTourClassPropertiesFieldsandMethodsMain
TocOrder: 15


---

Both properties and fields **store** and **retrieve** information in an object. At times, their similarity can make it difficult to determine which one is a better programming choice in a given case. 

Use **property** procedures when: 

- You need to control how and when a value is set or retrieved.
- Setting the value causes some change in the object's state, such as a visible
                property.
- Setting the property causes changes to other internal variables or to the
                values of other properties.
- The property has a well-defined set of values that need to be validated.
- A set of steps must be performed before the property can be set or retrieved.
                <br />

Use **fields** when: 

- The value is of a self-validating type. For example, an error or automatic data
                conversion occurs if a value other than **```True```** 
                or **```False```** 
                is assigned to a ```*Boolean```
                variable.
- The property is a ```*String``` data type, and there are no constraints on the
                size or value of the string.

### See Also
[Data Types (Conceptual)](aerConDataTypes.html)

[Data Types (Language Reference)](aerLrfDataTypesMain.html)

[Properties and Property Procedures](aerTourPropertiesandPropertyProcedures.html) 

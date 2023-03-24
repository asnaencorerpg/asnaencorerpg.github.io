---
title: PropVal

Id: Star_PROPVAL
TocParent: aerLrfSpecialValuesMain
TocOrder: 2


---

The * **PropVal** special value contains the value of a property when it is set when using [BEGPROP](BEGPROP.html). See example below with comments // Using *Propval. 

You can also define a name for * **PropVal** , and then just reference that name using the NewValname parameter. See example below with comments // Using NewValname. 

### Example

```
// Below is variable to maintain the value of MyProp property
DCLFLD MyPropVariable Type(*Zoned) Len(9,0) Access(*Public)

// Using *Propval
BEGPROP MyProp EVENT(*SET) Type(*Integer) Len(4) Access (*PUBLIC)
  MyPropVariable = *PropVal
ENDPROP

// Using NewValName
BEGPROP MyProp EVENT(*SET) Type(*Integer) 
Len(4) Access(*PUBLIC) NewValName (MyPropVal)
  MyPropVariable = MyPropVal
ENDPROP     
```

### See Also
[BEGPROP](BEGPROP.html) 

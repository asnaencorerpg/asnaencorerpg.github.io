---
title: "*Timestamp Data Type"

Id: Timestamp_Data_Type
TocParent: aerLrfDataTypesMain
TocOrder: 19


---

**Timestamp** fields have a predetermined size and format. They can be defined on the definition specification and must be in the following format: 

**yyyy-mm-dd-hh.mm.ss.mmmmmm (length 26)** // This is *ISO 

Microseconds (.mmmmmm) are optional for **Timestamp** **literals** and if not provided will be padded on the right with zeros. Leading zeros are required for all timestamp data. 

The following are the default, ***LOVAL** and ***HIVAL** values for ***Timestamp** data type. 

- The default initialization value for a timestamp is midnight of January 1, 0001 (0001-01-01-00.00.00.000000).
- The [*LOVAL](STARLOVAL.html) value for timestamp is 0001-01-01-00.00.00.000000.
- The [*HIVAL](STARHIVAL.html) value for a timestamp is 9999-12-31-24.00.00.000000.

*ISO is the only valid type for a * **Timestamp** data type. 

The equivalent .NET data type is . 

### Remarks
Design-time controls (DTC's) are no longer supported.

### See Also
[Date and Time](aerLrfDateandTimeMain.html)
[Data Types](aerLrfDataTypesMain.html)
[*LOVAL](STARLOVAL.html)
[*HIVAL](STARHIVAL.html) <br /> 

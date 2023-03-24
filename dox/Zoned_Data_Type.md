---
title: "*Zoned Data Type"

Id: Zoned_Data_Type
TocParent: aerLrfDataTypesMain
TocOrder: 20


---

The * **Zoned** data type means that each byte of storage can contain one digit or one character. In the zoned-decimal format, each byte of storage is divided into two portions: a 4-bit zone portion and a 4-bit digit portion. The zoned-decimal format looks like this: 

The **zone** portion of the low-order byte indicates the sign (positive or negative) of the decimal number. The standard signs are used: hexadecimal **F** for positive numbers and hexadecimal **D** for negative numbers. In zoned-decimal format, each digit in a decimal number includes a zone portion; however, only the low-order zone portion serves as the sign. 

You can specify an alternative sign format for zoned-decimal format. In the alternative sign format, the numeric field is immediately preceded or followed by a + or - sign. A plus sign is a hexadecimal 4E, and a minus sign is a hexadecimal 60. 

When an alternative sign format is specified, the field length (specified on the input specification) must include an additional position for the sign. For example, if a field is 5 digits long and the alternative sign format is specified, a field length of 6 positions must be specified. 

### See Also
[Data Types](aerLrfDataTypesMain.html) 

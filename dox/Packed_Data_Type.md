---
title: "*Packed Data Type"

Id: Packed_Data_Type
TocParent: aerLrfDataTypesMain
TocOrder: 16


---

The * **Packed** data type means that each byte of storage (except for the low order byte) can contain two decimal numbers. The low-order byte contains one digit in the left-most portion and the sign (positive or negative) in the right-most portion. The standard signs are used: hexadecimal **F** for positive numbers and hexadecimal **D** for negative numbers. 

The sign portion of the low-order byte indicates whether the numeric value represented in the digit portions is positive or negative. 

In ECR, the maximum length for a packed field is 28,0. 

### See Also
[Data Types](ecrLrfDataTypesMain.html) 

---
title: Multiple Occurrence Data Structures

Id: Mult_Occur_DS
TocParent: aerLrfLangElementsMain
TocOrder: 5


---

**Multiple Occurrence Data Structures** by default behave the same as in RPG/400. The current occurrence is initially set to the first and can be changed using the [OCCUR](OCCUR.html) operation code or [%OCCUR](OCCUR_Function.html) function. They can be declared using the [DCLDS](DCLDS.html) command. 

Encore RPG also allows the [ ] characters to access occurrences. Use of the [ ] does not alter the current occurrence. 

### Example
<table id="Table2" style="border-spacing: 0px" cellspacing="0" width="408" x-use-null-cells="x-use-null-cells" height="80"> <tbody class="Code"> <tr valign="top" style="x-cell-content-align: top"> <td colspan="1" rowspan="1" width="48"> MOVE </td> <td colspan="1" rowspan="1" width="66"> Total </td> <td colspan="1" rowspan="1" width="250"> MyDS[5].Total </td> </tr> <tr valign="top" style="x-cell-content-align: top"> <td colspan="1" rowspan="1" width="48"> MOVE </td> <td colspan="1" rowspan="1" width="66"> Prod </td> <td colspan="1" rowspan="1" width="250"> MyDS[5].ProdArray[3] </td> </tr> <tr valign="top" style="x-cell-content-align: top"> <td colspan="1" rowspan="1" width="48"> MOVE </td> <td colspan="1" rowspan="1" width="66"> Amount </td> <td colspan="1" rowspan="1" width="250"> MyMultDCLFLDDS[5,3,2].Amount </td> </tr> </tbody> </table> 

### See Also
[Language Elements](aerLrfLangElementsMain.html)

[Data Structure Element](DS_Element.html)

[DCLDS](DCLDS.html)

[DCLDSFLD](DCLDSFLD.html)

[DCLOVERLAYGROUP](DCLOVERLAYGROUP.html)

[OCCUR](OCCUR.html)

[%OCCUR](OCCUR_Function.html)

[Array Elements](Array_Element.html)

[Control Properties](Control_Properties.html)

[Fields](Field.html) 

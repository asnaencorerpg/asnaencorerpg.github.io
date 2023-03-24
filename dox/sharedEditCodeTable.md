---
title: Edit Code Table

Id: sharedEditCodeTable
TocParent: aerLrfEditCodeTable
TocOrder: 10


---

Using the **EditCode** property or keyword allows you to punctuate numeric fields, including $ signs, commas, periods, minus sign, and floating minus according to the standard RPG edit code rules. Enter a valid edit code as listed in the table below that gives you the desired display. For example, using EditCode **J** will display .00, giving you commas, decimals points, and a minus sign when necessary. 
<br />
<table class="tablediv" width="80%" border="border">
            <tr>
                <th align="CENTER" colspan="4" rowspan="1" valign="BOTTOM" id="COL1" width="41%">
                </th>
                <th align="CENTER" colspan="4" rowspan="1" valign="BOTTOM" id="COL5" width="45%">
                    Display<br />
                    (assuming US Regional Settings)
                </th>
            </tr>
            <tr>
                <th align="LEFT" colspan="1" rowspan="1" valign="TOP" id="WQ188" width="7%">
                    Edit Code
                </th>
                <th align="LEFT" colspan="1" rowspan="1" valign="TOP" id="COL2" width="11%">
                    Commas
                </th>
                <th align="LEFT" colspan="1" rowspan="1" valign="TOP" id="COL3" width="11%">
                    Decimal Point
                </th>
                <th align="LEFT" colspan="1" rowspan="1" valign="TOP" id="COL4" width="11%">
                    Sign for Negative Balance
                </th>
                <th align="CENTER" colspan="1" rowspan="1" valign="TOP" id="WQ189" width="11%">
                    "."
                </th>
                <th align="LEFT" colspan="1" rowspan="1" valign="TOP" id="WQ190" width="14%">
                    Zero Suppress
                </th>
            </tr>
            <tr>
                <td align="CENTER" colspan="1" headers="COL1 WQ188" rowspan="1" valign="TOP" width="7%">
                    1
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL2" rowspan="1" valign="TOP" width="11%">
                    Yes
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL3" rowspan="1" valign="TOP" width="11%">
                    Yes
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL4" rowspan="1" valign="TOP" width="11%">
                    No Sign
                </td>
                <td align="CENTER" colspan="1" headers="COL5 WQ189" rowspan="1" valign="TOP" width="11%">
                    .00 or 0
                </td>
                <td align="CENTER" colspan="1" headers="COL9 WQ190" rowspan="1" valign="TOP" width="14%">
                    Yes
                </td>
            </tr>
            <tr>
                <td align="CENTER" colspan="1" headers="COL1 WQ188" rowspan="1" valign="TOP" width="7%">
                    2
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL2" rowspan="1" valign="TOP" width="11%">
                    Yes
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL3" rowspan="1" valign="TOP" width="11%">
                    Yes
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL4" rowspan="1" valign="TOP" width="11%">
                    No Sign
                </td>
                <td align="CENTER" colspan="1" headers="COL5 WQ189" rowspan="1" valign="TOP" width="11%">
                    Blanks
                </td>
                <td align="CENTER" colspan="1" headers="COL9 WQ190" rowspan="1" valign="TOP" width="14%">
                    Yes
                </td>
            </tr>
            <tr>
                <td align="CENTER" colspan="1" headers="COL1 WQ188" rowspan="1" valign="TOP" width="7%">
                    3
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL2" rowspan="1" valign="TOP" width="11%">
                    <br />
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL3" rowspan="1" valign="TOP" width="11%">
                    Yes
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL4" rowspan="1" valign="TOP" width="11%">
                    No Sign
                </td>
                <td align="CENTER" colspan="1" headers="COL5 WQ189" rowspan="1" valign="TOP" width="11%">
                    .00 or 0
                </td>
                <td align="CENTER" colspan="1" headers="COL9 WQ190" rowspan="1" valign="TOP" width="14%">
                    Yes
                </td>
            </tr>
            <tr>
                <td align="CENTER" colspan="1" headers="COL1 WQ188" rowspan="1" valign="TOP" width="7%">
                    4
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL2" rowspan="1" valign="TOP" width="11%">
                    <br />
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL3" rowspan="1" valign="TOP" width="11%">
                    Yes
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL4" rowspan="1" valign="TOP" width="11%">
                    No Sign
                </td>
                <td align="CENTER" colspan="1" headers="COL5 WQ189" rowspan="1" valign="TOP" width="11%">
                    Blanks
                </td>
                <td align="CENTER" colspan="1" headers="COL9 WQ190" rowspan="1" valign="TOP" width="14%">
                    Yes
                </td>
            </tr>
            <tr>
                <td align="CENTER" colspan="1" headers="COL1 WQ188" rowspan="1" valign="TOP" width="7%">5-9<sup>1</sup></td>
                <td align="CENTER" colspan="1" headers="COL1 COL2" rowspan="1" valign="TOP" width="11%">
                    <br />
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL3" rowspan="1" valign="TOP" width="11%">
                    <br />
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL4" rowspan="1" valign="TOP" width="11%">
                    <br />
                </td>
                <td align="CENTER" colspan="1" headers="COL5 WQ189" rowspan="1" valign="TOP" width="11%">
                    <br />
                </td>
                <td align="CENTER" colspan="1" headers="COL9 WQ190" rowspan="1" valign="TOP" width="14%">
                    <br />
                </td>
            </tr>
            <tr>
                <td align="CENTER" colspan="1" headers="COL1 WQ188" rowspan="1" valign="TOP" width="7%">
                    A
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL2" rowspan="1" valign="TOP" width="11%">
                    Yes
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL3" rowspan="1" valign="TOP" width="11%">
                    Yes
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL4" rowspan="1" valign="TOP" width="11%">
                    CR
                </td>
                <td align="CENTER" colspan="1" headers="COL5 WQ189" rowspan="1" valign="TOP" width="11%">
                    .00 or 0
                </td>
                <td align="CENTER" colspan="1" headers="COL9 WQ190" rowspan="1" valign="TOP" width="14%">
                    Yes
                </td>
            </tr>
            <tr>
                <td align="CENTER" colspan="1" headers="COL1 WQ188" rowspan="1" valign="TOP" width="7%">
                    B
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL2" rowspan="1" valign="TOP" width="11%">
                    Yes
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL3" rowspan="1" valign="TOP" width="11%">
                    Yes
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL4" rowspan="1" valign="TOP" width="11%">
                    CR
                </td>
                <td align="CENTER" colspan="1" headers="COL5 WQ189" rowspan="1" valign="TOP" width="11%">
                    Blanks
                </td>
                <td align="CENTER" colspan="1" headers="COL9 WQ190" rowspan="1" valign="TOP" width="14%">
                    Yes
                </td>
            </tr>
            <tr>
                <td align="CENTER" colspan="1" headers="COL1 WQ188" rowspan="1" valign="TOP" width="7%">
                    C
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL2" rowspan="1" valign="TOP" width="11%">
                    <br />
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL3" rowspan="1" valign="TOP" width="11%">
                    Yes
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL4" rowspan="1" valign="TOP" width="11%">
                    CR
                </td>
                <td align="CENTER" colspan="1" headers="COL5 WQ189" rowspan="1" valign="TOP" width="11%">
                    .00 or 0
                </td>
                <td align="CENTER" colspan="1" headers="COL9 WQ190" rowspan="1" valign="TOP" width="14%">
                    Yes
                </td>
            </tr>
            <tr>
                <td align="CENTER" colspan="1" headers="COL1 WQ188" rowspan="1" valign="TOP" width="7%">
                    D
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL2" rowspan="1" valign="TOP" width="11%">
                    <br />
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL3" rowspan="1" valign="TOP" width="11%">
                    Yes
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL4" rowspan="1" valign="TOP" width="11%">
                    CR
                </td>
                <td align="CENTER" colspan="1" headers="COL5 WQ189" rowspan="1" valign="TOP" width="11%">
                    Blanks
                </td>
                <td align="CENTER" colspan="1" headers="COL9 WQ190" rowspan="1" valign="TOP" width="14%">
                    Yes
                </td>
            </tr>
            <tr>
                <td align="CENTER" colspan="1" headers="COL1 WQ188" rowspan="1" valign="TOP" width="7%">
                    J
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL2" rowspan="1" valign="TOP" width="11%">
                    Yes
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL3" rowspan="1" valign="TOP" width="11%">
                    Yes
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL4" rowspan="1" valign="TOP" width="11%">
                    - (minus)
                </td>
                <td align="CENTER" colspan="1" headers="COL5 WQ189" rowspan="1" valign="TOP" width="11%">
                    .00 or 0
                </td>
                <td align="CENTER" colspan="1" headers="COL9 WQ190" rowspan="1" valign="TOP" width="14%">
                    Yes
                </td>
            </tr>
            <tr>
                <td align="CENTER" colspan="1" headers="COL1 WQ188" rowspan="1" valign="TOP" width="7%">
                    K
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL2" rowspan="1" valign="TOP" width="11%">
                    Yes
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL3" rowspan="1" valign="TOP" width="11%">
                    Yes
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL4" rowspan="1" valign="TOP" width="11%">
                    - (minus)
                </td>
                <td align="CENTER" colspan="1" headers="COL5 WQ189" rowspan="1" valign="TOP" width="11%">
                    Blanks
                </td>
                <td align="CENTER" colspan="1" headers="COL9 WQ190" rowspan="1" valign="TOP" width="14%">
                    Yes
                </td>
            </tr>
            <tr>
                <td align="CENTER" colspan="1" headers="COL1 WQ188" rowspan="1" valign="TOP" width="7%">
                    L
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL2" rowspan="1" valign="TOP" width="11%">
                    <br />
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL3" rowspan="1" valign="TOP" width="11%">
                    Yes
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL4" rowspan="1" valign="TOP" width="11%">
                    - (minus)
                </td>
                <td align="CENTER" colspan="1" headers="COL5 WQ189" rowspan="1" valign="TOP" width="11%">
                    .00 or 0
                </td>
                <td align="CENTER" colspan="1" headers="COL9 WQ190" rowspan="1" valign="TOP" width="14%">
                    Yes
                </td>
            </tr>
            <tr>
                <td align="CENTER" colspan="1" headers="COL1 WQ188" rowspan="1" valign="TOP" width="7%">
                    M
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL2" rowspan="1" valign="TOP" width="11%">
                    <br />
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL3" rowspan="1" valign="TOP" width="11%">
                    Yes
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL4" rowspan="1" valign="TOP" width="11%">
                    - (minus)
                </td>
                <td align="CENTER" colspan="1" headers="COL5 WQ189" rowspan="1" valign="TOP" width="11%">
                    Blanks
                </td>
                <td align="CENTER" colspan="1" headers="COL9 WQ190" rowspan="1" valign="TOP" width="14%">
                    Yes
                </td>
            </tr>
            <tr>
                <td align="CENTER" colspan="1" headers="COL1 WQ188" rowspan="1" valign="TOP" width="7%">
                    N
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL2" rowspan="1" valign="TOP" width="11%">
                    Yes
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL3" rowspan="1" valign="TOP" width="11%">
                    Yes
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL4" rowspan="1" valign="TOP" width="11%">
                    - (floating minus)
                </td>
                <td align="CENTER" colspan="1" headers="COL5 WQ189" rowspan="1" valign="TOP" width="11%">
                    .00 or 0
                </td>
                <td align="CENTER" colspan="1" headers="COL9 WQ190" rowspan="1" valign="TOP" width="14%">
                    Yes
                </td>
            </tr>
            <tr>
                <td align="CENTER" colspan="1" headers="COL1 WQ188" rowspan="1" valign="TOP" width="7%">
                    O
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL2" rowspan="1" valign="TOP" width="11%">
                    Yes
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL3" rowspan="1" valign="TOP" width="11%">
                    Yes
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL4" rowspan="1" valign="TOP" width="11%">
                    - (floating minus)
                </td>
                <td align="CENTER" colspan="1" headers="COL5 WQ189" rowspan="1" valign="TOP" width="11%">
                    Blanks
                </td>
                <td align="CENTER" colspan="1" headers="COL9 WQ190" rowspan="1" valign="TOP" width="14%">
                    Yes
                </td>
            </tr>
            <tr>
                <td align="CENTER" colspan="1" headers="COL1 WQ188" rowspan="1" valign="TOP" width="7%">
                    P
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL2" rowspan="1" valign="TOP" width="11%">
                    <br />
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL3" rowspan="1" valign="TOP" width="11%">
                    Yes
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL4" rowspan="1" valign="TOP" width="11%">
                    - (floating minus)
                </td>
                <td align="CENTER" colspan="1" headers="COL5 WQ189" rowspan="1" valign="TOP" width="11%">
                    .00 or 0
                </td>
                <td align="CENTER" colspan="1" headers="COL9 WQ190" rowspan="1" valign="TOP" width="14%">
                    Yes
                </td>
            </tr>
            <tr>
                <td align="CENTER" colspan="1" headers="COL1 WQ188" rowspan="1" valign="TOP" width="7%">
                    Q
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL2" rowspan="1" valign="TOP" width="11%">
                    <br />
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL3" rowspan="1" valign="TOP" width="11%">
                    Yes
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL4" rowspan="1" valign="TOP" width="11%">
                    - (floating minus)
                </td>
                <td align="CENTER" colspan="1" headers="COL5 WQ189" rowspan="1" valign="TOP" width="11%">
                    Blanks
                </td>
                <td align="CENTER" colspan="1" headers="COL9 WQ190" rowspan="1" valign="TOP" width="14%">
                    Yes
                </td>
            </tr>
            <tr>
                <td align="CENTER" colspan="1" headers="COL1 WQ188" rowspan="1" valign="TOP" width="7%">X<sup>2</sup></td>
                <td align="CENTER" colspan="1" headers="COL1 COL2" rowspan="1" valign="TOP" width="11%">
                    <br />
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL3" rowspan="1" valign="TOP" width="11%">
                    <br />
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL4" rowspan="1" valign="TOP" width="11%">
                    <br />
                </td>
                <td align="CENTER" colspan="1" headers="COL5 WQ189" rowspan="1" valign="TOP" width="11%">
                    <br />
                </td>
                <td align="CENTER" colspan="1" headers="COL9 WQ190" rowspan="1" valign="TOP" width="14%">
                    <br />
                </td>
            </tr>
            <tr>
                <td align="CENTER" colspan="1" headers="COL1 WQ188" rowspan="1" valign="TOP" width="7%">Y<sup>3</sup></td>
                <td align="CENTER" colspan="1" headers="COL1 COL2" rowspan="1" valign="TOP" width="11%">
                    <br />
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL3" rowspan="1" valign="TOP" width="11%">
                    <br />
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL4" rowspan="1" valign="TOP" width="11%">
                    <br />
                </td>
                <td align="CENTER" colspan="1" headers="COL5 WQ189" rowspan="1" valign="TOP" width="11%">
                    <br />
                </td>
                <td align="CENTER" colspan="1" headers="COL9 WQ190" rowspan="1" valign="TOP" width="14%">
                    Yes
                </td>
            </tr>
            <tr>
                <td align="CENTER" colspan="1" headers="COL1 WQ188" rowspan="1" valign="TOP" width="7%">Z<sup>4</sup></td>
                <td align="CENTER" colspan="1" headers="COL1 COL2" rowspan="1" valign="TOP" width="11%">
                    <br />
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL3" rowspan="1" valign="TOP" width="11%">
                    <br />
                </td>
                <td align="CENTER" colspan="1" headers="COL1 COL4" rowspan="1" valign="TOP" width="11%">
                    <br />
                </td>
                <td align="CENTER" colspan="1" headers="COL5 WQ189" rowspan="1" valign="TOP" width="11%">
                    <br />
                </td>
                <td align="CENTER" colspan="1" headers="COL9 WQ190" rowspan="1" valign="TOP" width="14%">
                    Yes
                </td>
            </tr>
            <tr>
                <td align="LEFT" colspan="9" headers="COL1 WQ188 COL1 COL2 COL1 COL3 COL1 COL4 COL5 WQ189 COL9 WQ190" rowspan="1" valign="TOP" width="80%">

**Notes:** 
<ol />

- These are the user-defined edit codes.
- The X edit code ensures a hexadecimal F sign for positive values.
                            Because the system does this for you, normally you do not have to specify this
                            code.
- The Y edit code suppresses the leftmost zeros of date fields, up to but
                            not including the digit preceding the first separator. The Y edit code
                            also inserts slashes (/) between the month, day, and year according to the
                            following pattern:
<pre>   nn/n
   nn/nn
   nn/nn/n
   nn/nn/nn
  nnn/nn/nn
   nn/nn/nnnn
  nnn/nn/nnnn
 nnnn/nn/nn
nnnnn/nn/nn
</pre>
- The Z edit code removes the sign (plus or minus) from a numeric field and
                            suppresses leading zeros.

</td>
            </tr>
</table>

### See Also
[EditWord Usage](sharedEditWordTable.html) <br /> 

---
title: Expression Overview with QrySelect

Id: Expression_Overview_with_QRYSELECT_or_Select_Omit_Rule
TocParent: Expressions
TocOrder: 3


---

An **expression** to be used with a **QrySelect** within [DCLDISKFILE](DCLDISKFILE.html) is a logical expression consisting of one or more relational expressions optionally combined with the "&amp;" (and) and "|" (or) operators. Since "&amp;" has a higher priority than "|", you can use parentheses to force the order in which the expression is evaluated. 

An **expression** is defined by a single or double quote, followed by any combination of characters, and terminated by a single or double quote. Note that a numeric field can be compared against numeric constants, and a character field must be compared against a **quoted character constant** . 

Please note that if you want a double quote within a literal, you must include two quotes. For example, to assign to a character field the value <pre>He said "Come NOW!".</pre>, The assignemnt would have to coded like this: <pre>phrase = "He said ""Come NOW!""."</pre> 

A **relational expression** consists of a field name, a relational operator and a constant or another field name. 

The valid relational operators are:<br /> 


| -------- | --- | ------------- |
| &lt;     | LT  | Less Than 
| &gt;     | GT  | Great Than 
| &lt;=    | LE  | Less Than or Equal To 
| &gt;=    | GE  | Greater Than or Equal To 
| =        | EQ  | Equal Condition 
| !=       | NE  | Not Equal Condition 
| &lt;&gt; | NE  | Not Equal Condition 
| &amp;    | AND | And 
| &#124;,  | OR  | Or 



The example below ( **Table 1** ) lists some example expressions, showing that if you want the expression to equal a particular character value, you must put double quotes around the value. Note that you do not need to specify quotes around a numeric value. 

The result of the expression is derived from the fields X, Y and Z as listed in table 2 below.

**Table 1**

<table id="Table3" style="MARGIN-LEFT: 24px; WIDTH: 312px; BORDER-COLLAPSE: separate; border-spacing: 0px; x-border-left: 1px table-solid; x-border-top: 1px table-solid; x-border-right: 1px table-solid; x-border-bottom: 1px table-solid" cellspacing="0" width="312" border="1" x-use-null-cells="x-use-null-cells"> <tr valign="top" style="x-cell-content-align: top"> 
<td colspan="1" rowspan="1" width="84" bgcolor="#e0e0e0"> 
<p align="center" style="MARGIN-LEFT: 0px; TEXT-ALIGN: center"> Expression </p>
</td>
        <td colspan="1" rowspan="1" width="150" bgcolor="#e0e0e0">

Explanation
</td>
        <td colspan="1" rowspan="1" width="78" bgcolor="#e0e0e0">

Result
</td>
        </tr>
        <tr valign="top" style="x-cell-content-align: top">
            <td colspan="1" rowspan="1" width="84">

"x = y" 
</td>
            <td colspan="1" rowspan="1" width="150">

The contents of field x = the contents of field y. 
</td>
            <td colspan="1" rowspan="1" width="78">

Record 2 
</td>
        </tr>
        <tr valign="top" style="x-cell-content-align: top">
            <td colspan="1" rowspan="1" width="84">

"x = ""y""" 
</td>
            <td colspan="1" rowspan="1" width="150">

The contents of field x = the character value Y. 
</td>
            <td colspan="1" rowspan="1" width="78">

Record 5 
</td>
        </tr>
        <tr valign="top" style="x-cell-content-align: top">
            <td colspan="1" rowspan="1" width="84">

"Z = 4" 
</td>
            <td colspan="1" rowspan="1" width="150">

The contents of field Z = the value 4. 
</td>
            <td colspan="1" rowspan="1" width="78">

Record 4 
</td>
        </tr>
</table>

**Table 2**

<table id="Table4" style="MARGIN-LEFT: 24px; WIDTH: 312px; BORDER-COLLAPSE: separate; border-spacing: 0px; x-border-left: 1px table-solid; x-border-top: 1px table-solid; x-border-right: 1px table-solid; x-border-bottom: 1px table-solid" cellspacing="0" width="312" border="1" x-use-null-cells="x-use-null-cells"> <tr valign="top" style="x-cell-content-align: top"> <td colspan="1" rowspan="1" width="84" bgcolor="#e0e0e0"> 

<p align="center" style="MARGIN-LEFT: 0px; TEXT-ALIGN: center"> Field X </p>
</td>
        <td colspan="1" rowspan="1" width="114" bgcolor="#e0e0e0">

Field Y
</td>
        <td colspan="1" rowspan="1" width="114" bgcolor="#e0e0e0">

Field Z
</td>
        </tr>
        <tr valign="top" style="x-cell-content-align: top">
            <td colspan="1" rowspan="1" width="84">

A 
</td>
            <td colspan="1" rowspan="1" width="114">

X 
</td>
            <td colspan="1" rowspan="1" width="114">

1 
</td>
        </tr>
        <tr valign="top" style="x-cell-content-align: top">
            <td colspan="1" rowspan="1" width="84">

B 
</td>
            <td colspan="1" rowspan="1" width="114">

B 
</td>
            <td colspan="1" rowspan="1" width="114">

2 
</td>
        </tr><tr valign="top" style="x-cell-content-align: top">
            <td colspan="1" rowspan="1" width="84">

C 
</td>
            <td colspan="1" rowspan="1" width="114">

Y 
</td>
            <td colspan="1" rowspan="1" width="114">

3 
</td>
        </tr>
        <tr valign="top" style="x-cell-content-align: top">
            <td colspan="1" rowspan="1" width="84">

X 
</td>
            <td colspan="1" rowspan="1" width="114">

C 
</td>
            <td colspan="1" rowspan="1" width="114">

4 
</td>
        </tr>
        <tr valign="top" style="x-cell-content-align: top">
            <td colspan="1" rowspan="1" width="84">

Y 
</td>
            <td colspan="1" rowspan="1" width="114">

Z 
</td>
            <td colspan="1" rowspan="1" width="114">

5 
</td>
        </tr>
        <tr valign="top" style="x-cell-content-align: top">
            <td colspan="1" rowspan="1" width="84">

Z 
</td>
            <td colspan="1" rowspan="1" width="114">

A 
</td>
            <td colspan="1" rowspan="1" width="114">

6 
</td>
        </tr>
</table>


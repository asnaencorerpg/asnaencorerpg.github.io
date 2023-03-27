---
title: Declared Element Characteristics

Id: aerConDeclaredElementCharacteristics
TocParent: aerConDeclaredElements
TocOrder: 0


---

Every *declared element* (a programming element that is defined in a declaration statement) has one or more of the following characteristics associated with it: 

- Data type - (```Type```
                keyword) The values the element can hold, and how those values are stored,
                such as ```
                    *BINARY, *BOOLEAN, *BYTE, *CHAR, *DATE, *DECIMAL | *FLOAT, *IND,
                    *INTEGER, *OBJECT, *ONECHAR, *PACKED,  *STRING, *TIME, *TIMESTAMP
                ```, or
                ```*ZONED```.
- Lifetime - (```Static```
                keyword) The period the declared field will remain in existence and
                retain their latest values after termination of the procedure in which they are
                declared.
- Scope - (```Access```
                keyword) The type of access to the member, such as ```
                    *PRIVATE, *PUBLIC,
                    *PROTECTED
                ```, or ```*INTERNAL```.
- Accessibility (```Shared``` keyword) The permission for code
                to use the element.<br />

The following table shows the declared elements and the characteristics that apply to each one. 
<br />

<table class="dtTABLE" id="Table2" cellspacing="0" width="85%">
                <tr valign="top">
                    <th colspan="1" rowspan="1" width="13%">
                        Element
                    </th>
                    <th colspan="1" rowspan="1" width="13%">
                        Data type<br />
                        (```Type```)
                    </th>
                    <th colspan="1" rowspan="1" width="13%">
                        Lifetime<br />
                        (```Static```)
                    </th>
                    <th colspan="1" rowspan="1" width="13%">
                        Scope<br />
                        (```Access```)
                    </th>
                    <th colspan="1" rowspan="1" width="13%">
                        Accessibility<br />
                        (```Shared```)
                    </th>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">Class</td>
                    <td colspan="1" rowspan="1">No</td>
                    <td colspan="1" rowspan="1">No</td>
                    <td colspan="1" rowspan="1">Yes</td>
                    <td colspan="1" rowspan="1">Yes</td>
                </tr>
                <tr valign="top">
                    <td colspan="1" rowspan="1">Constant</td>
                    <td colspan="1" rowspan="1">Yes</td>
                    <td colspan="1" rowspan="1">No</td>
                    <td colspan="1" rowspan="1">Yes</td>
                    <td colspan="1" rowspan="1">Yes</td>
                </tr>
                <tr valign="top">
                    <td colspan="1" rowspan="1" style="height: 22px">Enumeration</td>
                    <td colspan="1" rowspan="1" style="height: 22px">Yes</td>
                    <td colspan="1" rowspan="1" style="height: 22px">No</td>
                    <td colspan="1" rowspan="1" style="height: 22px">Yes</td>
                    <td colspan="1" rowspan="1" style="height: 22px">Yes</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">Event</td>
                    <td colspan="1" rowspan="1">No</td>
                    <td colspan="1" rowspan="1">No</td>
                    <td colspan="1" rowspan="1">Yes</td>
                    <td colspan="1" rowspan="1">Yes</td>
                </tr>
                <tr valign="top">
                    <td colspan="1" rowspan="1">Property</td>
                    <td colspan="1" rowspan="1">Yes</td>
                    <td colspan="1" rowspan="1">No</td>
                    <td colspan="1" rowspan="1">Yes</td>
                    <td colspan="1" rowspan="1">Yes</td>
                </tr>
                <tr valign="top">
                    <td colspan="1" rowspan="1">Method</td>
                    <td colspan="1" rowspan="1">No</td>
                    <td colspan="1" rowspan="1">No</td>
                    <td colspan="1" rowspan="1">Yes</td>
                    <td colspan="1" rowspan="1">Yes</td>
                </tr>
                <tr valign="top">
                    <td colspan="1" rowspan="1">Procedure</td>
                    <td colspan="1" rowspan="1">No</td>
                    <td colspan="1" rowspan="1">No</td>
                    <td colspan="1" rowspan="1">Yes</td>
                    <td colspan="1" rowspan="1">Yes</td>
                </tr>
                <tr valign="top">
                    <td colspan="1" rowspan="1">Function return</td>
                    <td colspan="1" rowspan="1">Yes</td>
                    <td colspan="1" rowspan="1">Yes</td>
                    <td colspan="1" rowspan="1">Yes</td>
                    <td colspan="1" rowspan="1">No</td>
                </tr>
                <tr valign="top">
                    <td colspan="1" rowspan="1">Delegate</td>
                    <td colspan="1" rowspan="1">No</td>
                    <td colspan="1" rowspan="1">No</td>
                    <td colspan="1" rowspan="1">Yes</td>
                    <td colspan="1" rowspan="1">Yes</td>
                </tr>
                <tr valign="top">
                    <td colspan="1" rowspan="1">Interface</td>
                    <td colspan="1" rowspan="1">No</td>
                    <td colspan="1" rowspan="1">No</td>
                    <td colspan="1" rowspan="1">Yes</td>
                    <td colspan="1" rowspan="1">Yes</td>
                </tr>
                <tr valign="top">
                    <td colspan="1" rowspan="1">Variable</td>
                    <td colspan="1" rowspan="1">Yes</td>
                    <td colspan="1" rowspan="1">Yes</td>
                    <td colspan="1" rowspan="1">Yes</td>
                    <td colspan="1" rowspan="1">Yes</td>
                </tr>
</table>

### Visibility
Visibility results from a combination of lifetime, scope, and accessibility. a programming element can be said to be *visible* from a block of code when all three of the following conditions apply: 

- The element is within its lifetime ( **Static** ) — that
                is, it has been created and not yet terminated.
- The **access** 
                of the element includes the block of code referring to it.
- The element's **sharing**  accessibility permits the code
                to use it.

### Related Sections

[Declared Element Lifetime](ecrConDeclaredElementsLifetime.html)

Describes the lifetime of a declared element.


[Declared Element Scope](ecrConDeclaredElementsScope.html)

Describes the scope of access of a declared element.


[Declared Element Accessibility](ecrConAccessibility.html)

Describes the accessibility of a declared element.



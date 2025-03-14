---
title: Data Type Summary

Id: Data_type_summary
TocParent: aerLrfDataTypesMain
TocOrder: 0


---

The following table shows the Encore RPG data types, their supporting common language runtime types, their nominal storage allocation, and their value ranges. 
<table class="dtTABLE" id="Table2" cellspacing="0">
                <tr valign="top">
                    <th colspan="1" rowspan="1" width="14%">
                        Encore RPG type<br />
                    </th>
                    <th colspan="1" rowspan="1" width="24%">
                        Common language runtime type structure
                    </th>
                    <th colspan="1" rowspan="1" width="16%">
                        Nominal storage allocation
                    </th>
                    <th colspan="1" rowspan="1" width="46%">
                        Value range<br />
                    </th>
                </tr>
                <tr valign="top">
                    <td colspan="1" rowspan="1">
 ***Boolean** 
                    </td>
                    <td colspan="1" rowspan="1">
                        [*Boolean Data Type](https://msdn.microsoft.com/en-us/library/system.boolean(v=vs.110).aspx">System.Boolean</a>
                    </td>
                    <td colspan="1" rowspan="1">
                        2 bytes
                    </td>
                    <td colspan="1" rowspan="1">
 **True**  or **False.** 
                    </td>
                </tr>
                <tr valign="top">
                    <td colspan="1" rowspan="1">
 ***Byte** 
                    </td>
                    <td colspan="1" rowspan="1">
                        <a href="https://msdn.microsoft.com/en-us/library/system.byte(v=vs.110).aspx">System.Byte</a>
                    </td>
                    <td colspan="1" rowspan="1">
                        1 byte
                    </td>
                    <td colspan="1" rowspan="1">
                        0 through 255 (unsigned).
                    </td>
                </tr>
                <tr valign="top">
                    <td colspan="1" rowspan="1">
 ***Char** 
                    </td>
                    <td colspan="1" rowspan="1">
                        <a href="https://msdn.microsoft.com/en-us/library/system.char(v=vs.110).aspx">System.Char</a>
                    </td>
                    <td colspan="1" rowspan="1">
                        2 bytes
                    </td>
                    <td colspan="1" rowspan="1">
                        0 through 65535 (unsigned).
                    </td>
                </tr>
                <tr valign="top">
                    <td colspan="1" rowspan="1">
 ***Date** 
                    </td>
                    <td colspan="1" rowspan="1">
                        <a href="https://msdn.microsoft.com/en-us/library/system.datetime(v=vs.110).aspx">System.DateTime</a>
                    </td>
                    <td colspan="1" rowspan="1">
                        8 bytes
                    </td>
                    <td colspan="1" rowspan="1">
                        0:00:00 on January 1, 0001 through 11:59:59 PM on December 31, 9999.
                    </td>
                </tr>
                <tr valign="top">
                    <td colspan="1" rowspan="1">
 ***Decimal** 
                    </td>
                    <td colspan="1" rowspan="1">
                        <a href="https://msdn.microsoft.com/en-us/library/system.decimal(v=vs.110).aspx">System.Decimal</a>
                    </td>
                    <td colspan="1" rowspan="1">
                        16 bytes
                    </td>
                    <td colspan="1" rowspan="1">
                        0 through +/-79,228,162,514,264,337,593,543,950,335 with no decimal point;
                        <br />
                        0 through +/-7.9228162514264337593543950335 with 28 places to the right of the
                        decimal; smallest nonzero number is
                        <br />
                        +/-0.0000000000000000000000000001 (+/-1E-28).
                    </td>
                </tr>
                <tr valign="top">
                    <td colspan="1" rowspan="1">
 ***Integer** 
                    </td>
                    <td colspan="1" rowspan="1">
                        <a href="https://msdn.microsoft.com/en-us/library/system.Int32(v=vs.110).aspx">System.Int32</a>
                    </td>
                    <td colspan="1" rowspan="1">
                        4 bytes
                    </td>
                    <td colspan="1" rowspan="1">
                        -2,147,483,648 through 2,147,483,647.
                    </td>
                </tr>
                <tr valign="top">
                    <td colspan="1" rowspan="1">
 ***Object** 
                    </td>
                    <td colspan="1" rowspan="1">
                        <a href="https://msdn.microsoft.com/en-us/library/system.Object(v=vs.110).aspx">System.Object</a> (class)
                    </td>
                    <td colspan="1" rowspan="1">
                        4 bytes
                    </td>
                    <td colspan="1" rowspan="1">
                        Any type can be stored in a variable of type **Object** .
                    </td>
                </tr>
                <tr valign="top">
                    <td colspan="1" rowspan="1">
 ***String** 
                        <br />
                        (variable-length)
                    </td>
                    <td colspan="1" rowspan="1">
                        <a href="https://msdn.microsoft.com/en-us/library/system.string(v=vs.110).aspx">System.String</a> (class)
                    </td>
                    <td colspan="1" rowspan="1">
                        Depends on implementing platform
                    </td>
                    <td colspan="1" rowspan="1">
                        0 to approximately 2 billion Unicode characters.
                    </td>
                </tr>
</table>

### Memory Consumption
When you declare an elementary data type, it is not safe to assume that its memory consumption is the same as its nominal storage allocation. The common language runtime assigns storage based on the characteristics of the platform on which your application is executing. In some circumstances it packs your declared elements as closely together as possible; in other cases it aligns their memory addresses to natural hardware boundaries. Also, storage assignment is different on a 64-bit platform than it is on a 32-bit platform. 

The same considerations apply to each member of a composite data type such as a structure or an array. Furthermore, some composite types have additional memory requirements. For example, an array uses extra memory for the array itself and also for each dimension. On a 32-bit platform, this overhead is currently 12 bytes plus 8 bytes for each dimension. On a 64-bit platform the requirement is doubled. You cannot rely on simply adding together the nominal storage allocations of the components. 

An **Object** referring to any elementary or composite data type uses 4 bytes in addition to the data contained in the data type. 

### See Also
<a href="Boolean_Data_Type.html)
[*Byte Data Type](Byte_Data_Type.html)

[*Char Data Type](Character_Data_Type.html)

[*Date Data Type](Date_Data_Type.html)

[*Integer Data Type](Integer_Data_Type.html)

[*String Data Type](String_Data_Type.html)

[.NET Framework Data Types Comparison](/concepts/datatypes/FrameworkDataTypesComparison.html) 

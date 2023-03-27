---
title: SETLL

Id: SETLL
TocParent: aerLrfOpCodesMain
TocOrder: 1460


---

Positions a file at the next record that has a key or relative record number that is greater than or equal to the search argument. 

```

 **SETLL
File** (file name | Format Name) **Key**  (KeyList Name | Character Expression | *START | *END)
NotFnd (Indicator Variable)
Err (*EXTENDED | Indicator Variable)
KeyEq (Indicator Variable)
```

### Parts

**File** 

Required. Must be a file name or format name.


**Key** 

Required. **Key** can be a field name, a named constant, a figurative constant, or a literal that is used as the search argument in positioning a file. You can also specify *START or *END to position the file at the beginning or end of a file. Refer to [%KDS](KDS_Function.html) to use this built-in function to establish search arguments (Key) for Data Structures. 

- *START - positions the file at the beginning of file, so the **READ** returns the 1st record.
- *END - positions the file at the end of the file, so the **READP** returns the last record of the file.


**NotFnd** 

Optional. Indicator variable used to determine if the record was found while executing this command. 

Note that you can also use the [%FOUND](FOUND_Function.html) function.

However, be aware that **%FOUND** and the **NotFnd** indicator have **opposite** meanings: one will be **False** when the other one is **True** and vice versa.


**Err** 

Optional. Determines what the runtime will do if an error occurs while executing this command. The following rules apply: 

- **Err** (Indicator Variable) - The specified Indicator is set if an error occurred.
- **Err** (*EXTENDED) - A program status flag is set whose status can be checked using the [%ERROR](ERROR_Function.html) built-in function.
- If the **Err** keyword is not given and an error occurs, a runtime exception will be thrown.


**KeyEq** 

Optional. This indicator is set on when a record is present whose key or relative record number is equal to the search argument. This information can also be obtained from the [%EQUAL](EQUAL_Function.html) built-in function, which returns **True** if an exact match is found. 

If the file is a multiformat file accessed by RRN, you cannot perform the operation using the file name, you must use the format name.


### Remarks
If you want to process a "Range" of records, you could use the [SETRANGE](SETRANGE.html) op code. This op code is especially useful in increasing performance and speed when you are working with large files. Also, if you will be accessing SQL files, you definitely want to use **SETRANGE** . The **SETRANGE** op code allows you to specify a range of records to process by specifying a first and last key. However, the last key defaults to the same as the FirstKey, so if you are only searching 1 key, you basically just change the **SETLL** . 

### Example
/* In this example, the file OrderMasterFile contains order records. The key field is the order number (OrderNumber) field. There are multiple records for each order. OrderMasterFile looks like this. */ 

<span style="FONT-WEIGHT: bold"> OrderMasterFile </span> 
<table id="Table2" style="MARGIN-LEFT: 4.5pt; WIDTH: 198px; border-spacing: 0px" cellspacing="0" width="198" x-use-null-cells="x-use-null-cells">
            <tr valign="top" style="x-cell-content-align: top">
                <td colspan="1" rowspan="1" width="72" bgcolor="#e0e0e0">

** Order ** 
</td>
                <td colspan="1" rowspan="1" width="126" bgcolor="#e0e0e0">

** Other fields ** 
</td>
            </tr>
            <tr valign="top" style="x-cell-content-align: top">
                <td colspan="1" rowspan="1" width="72">

100 
</td>
                <td colspan="1" rowspan="1" width="126">

1st record of 100 
</td>
            </tr>
            <tr valign="top" style="x-cell-content-align: top">
                <td colspan="1" rowspan="1" width="72">

100 
</td>
                <td colspan="1" rowspan="1" width="126">

2nd record of 100 
</td>
            </tr>
            <tr valign="top" style="x-cell-content-align: top">
                <td colspan="1" rowspan="1" width="72">

(SETLL) 

100 
</td>
                <td colspan="1" rowspan="1" width="126">

3rd record of 100 
</td>
            </tr>
            <tr valign="top" style="x-cell-content-align: top">
                <td colspan="1" rowspan="1" width="72">

101 
</td>
                <td colspan="1" rowspan="1" width="126">

1st record of 101 
</td>
            </tr>
            <tr valign="top" style="x-cell-content-align: top">
                <td colspan="1" rowspan="1" width="72">

101 
</td>
                <td colspan="1" rowspan="1" width="126">

2nd record of 101 
</td>
            </tr>
            <tr valign="top" style="x-cell-content-align: top">
                <td colspan="1" rowspan="1" width="72">

101 
</td>
                <td colspan="1" rowspan="1" width="126">

3rd record of 101 
</td>
            </tr>
            <tr valign="top" style="x-cell-content-align: top">
                <td colspan="1" rowspan="1" width="72">

101 
</td>
                <td colspan="1" rowspan="1" width="126">

4th record of 101 
</td>
            </tr>
            <tr valign="top" style="x-cell-content-align: top">
                <td colspan="1" rowspan="1" width="72">

102 
</td>
                <td colspan="1" rowspan="1" width="126">

1st record of 102 
</td>
            </tr>
</table>
        
```
/* All the 101 records in OrderMasterFile are to be printed. The value 101 has previously been placed in OrderNumber. 
   The SETLL operation positions the file at the first record with the key value 101 and indicator 55 is set on.*/ 

SetLL OrderMasterFile OrderNumber NotFnd(*In55) Err (*In99) 

/* The following DO loop processes all the records that have the same key value. Indicator 55 is used for conditioning
    the DO loop.*/ 

*If *In55 = *Off
Dountil *In56 = *On
Reade OrderMasterFile OrderNumber Eof(*In56)
Write DetailPrintLine
Enddo
Endif 
```

The READE operation reads the second, third, and fourth 101 records in the same manner as the first 101 record was read. After the fourth 101 record is read, the READE operation is attempted. Because the 102 record is not of the same group, indicator 56 is set on, the Write operation is bypassed and the Dountil loop ends. 

### See Also
[CHAIN](CHAIN.html)

[READE](READE.html)

[READRANGE](READRANGE.html)

[SETGT](SETGT.html)

[SETRANGE](SETRANGE.html)

[*START](START.html)

[*END](StarEND.html)

[%ERROR](ERROR_Function.html)

[%EQUAL](EQUAL_Function.html)

[%FOUND](FOUND_Function.html)

[%KDS](KDS_Function.html) 

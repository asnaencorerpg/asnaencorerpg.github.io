---
title: SETGT

Id: SETGT
TocParent: aerLrfOpCodesMain
TocOrder: 1450


---

Positions a file at the next record with a key or relative record number that is greater than the key or relative record number specified in Key. 

```
SETGT
File (file name | Format Name) Key  (KeyList Name | Character Expression)     
NotFnd (Indicator Variable)
Err (*EXTENDED | Indicator Variable)
```

### Parameters

**File** 

Required. Must be a file name or format name.


**Key** 

Required. **Key** can be a field name, a named constant, a figurative constant, or a literal that is used as the search argument in positioning a file. Refer to [%KDS](KDS_Function.html) to use this built-in function to establish search arguments (Key) for Data Structures.


**NotFnd** 

Optional. NotFnd uses an Indicator variable to determine if the record was found while executing this command. 

Note that you can also use the [%FOUND](FOUND_Function.html) function. However, be aware that %FOUND and the NotFnd indicator have **opposite** meanings: one will be **False** when the other one is **True** and vice versa.


**Err** 

Optional. Err determines what the runtime will do if an error occurs while executing this command. The following rules apply: 

- **Err** (Indicator Variable) - The specified Indicator is set if an error occurred.
- **Err** (*EXTENDED) - A program status flag is set whose status can be checked using the [%ERROR](ERROR_Function.html) built-in function.
- If the **Err** keyword is not given and an error occurs, a runtime exception will be thrown.


### Remarks
If the file is a multiformat file accessed by RRN, you cannot perform the operation using the file name, you must use the format name. 

Following the **SETGT** operation, a file is positioned so that it is immediately before the first record whose key or relative record number is greater than the search argument specified in **Key** . Read the file to retrieve this record. However, before you read the file, records may be deleted from the file by another job or through another file in your job. Thus, you may not get the expected record. 

### Example
/* This example shows how to position the file so READ will read the next record. The search argument, ITEMNUMBER, specified for the **SETGT** operation has a value of 98; therefore, **SETGT** positions the file before the first record of file format ITEMMASTER that has a key field value greater than 98. The file is positioned before the first record with a key value of 100. The READ operation reads the record that has a value of 100 in its key field. */ 

```
DclFld NotFound *Ind
DclFld ErrorOnSet *Ind
DclFld EndOfFile *Ind 

 **SETGT** ItemMaster ItemNumber Err (ErrorOnSet) NotFnd(NotFound)
If NotFound = *Off *And ErrorOnSet = *Off   
    Read ItemMaster Eof(EndOfFile)
Endif
```
/* This example shows how to read the last record of a group of records with the same key value and format from a program Described file. The search argument, ITEMNUMBER, specified for the **SETGT** operation positions the file before the first record of file PARTMASTER that has a key field value greater than 70. The file is positioned before the first record with a key value of 80. The READP operation reads the last record that has a value of 70 in its key field. */ 

```
DclFld NotFound *Ind
DclFld ErrorOnSet *Ind
DclFld EndOfFile *Ind
 **SETGT**  PartMaster ItemNumber Err (ErrorOnSet) NotFnd(NotFound)
If NotFound = *Off *And ErrorOnSet = *Off  
    Read PartMaster Eof(EndOfFile)
Endif
```
<table class="fineprint" id="Table3" style="WIDTH: 456px; border-spacing: 0px" cellspacing="0" width="456" x-use-null-cells="x-use-null-cells">
            <tbody class="normal">
                <tr valign="top" style="x-cell-content-align: top">
                    <td colspan="1" rowspan="1" width="86">
                    </td>
                    <td align="center" colspan="1" rowspan="1" width="63">
 **key field<br />
                            Values** 
                    </td>
                    <td colspan="1" rowspan="1" width="150">
                    </td>
                    <td align="center" colspan="1" rowspan="1" width="63">
 **key field<br />
                            Values** 
                    </td>
                    <td colspan="1" rowspan="1" width="63">
                    </td>
                </tr>
                <tr valign="top" style="x-cell-content-align: top">
                    <td colspan="1" rowspan="1" width="86">
                    </td>
                    <td align="center" colspan="1" rowspan="1" width="63">
                        97
                    </td>
                    <td colspan="1" rowspan="1" width="150">
                    </td>
                    <td align="center" colspan="1" rowspan="1" width="63">
                        50
                    </td>
                    <td colspan="1" rowspan="1" width="63">
                    </td>
                </tr>
                <tr valign="top" style="x-cell-content-align: top">
                    <td colspan="1" rowspan="1" width="86">
                    </td>
                    <td align="center" colspan="1" rowspan="1" width="63">
                        97
                    </td>
                    <td colspan="1" rowspan="1" width="150">
                    </td>
                    <td align="center" colspan="1" rowspan="1" width="63">
                        60
                    </td>
                    <td colspan="1" rowspan="1" width="63">
                    </td>
                </tr>
                <tr valign="top" style="x-cell-content-align: top">
                    <td colspan="1" rowspan="1" width="86">
                    </td>
                    <td align="center" colspan="1" rowspan="1" width="63">
                        97
                    </td>
                    <td colspan="1" rowspan="1" width="150">
                    </td>
                    <td align="center" colspan="1" rowspan="1" width="63">
                        70
                    </td>
                    <td colspan="1" rowspan="1" width="63">
                    </td>
                </tr>
                <tr valign="top" style="x-cell-content-align: top">
                    <td colspan="1" rowspan="1" width="86">
                    </td>
                    <td align="center" colspan="1" rowspan="1" width="63">
                        97
                    </td>
                    <td align="right" colspan="1" rowspan="1" width="150">
                        (READP)
                    </td>
                    <td align="center" colspan="1" rowspan="1" width="63">
                        70
                    </td>
                    <td colspan="1" rowspan="1" width="63">
                    </td>
                </tr>
                <tr valign="top" style="x-cell-content-align: top">
                    <td colspan="1" rowspan="1" width="86">
                    </td>
                    <td align="center" colspan="1" rowspan="1" width="63">
                        98
                    </td>
                    <td colspan="1" rowspan="1" width="150">ITEMMASTER (SETGT) </td>
                    <td align="center" colspan="1" rowspan="1" width="63">
                        80
                    </td>
                    <td colspan="1" rowspan="1" width="63">
                        PARTMASTER
                    </td>
                </tr>
                <tr valign="top" style="x-cell-content-align: top">
                    <td align="right" colspan="1" rowspan="1" width="86" style="height: 36px">
 (SETGT) (READ)
                    </td>
                    <td align="center" colspan="1" rowspan="1" width="63" style="height: 36px">
                        100
                    </td>
                    <td colspan="1" rowspan="1" width="150" style="height: 36px">
                    </td>
                    <td align="center" colspan="1" rowspan="1" width="63" style="height: 36px">
                        80
                    </td>
                    <td colspan="1" rowspan="1" width="63" style="height: 36px">
                    </td>
                </tr>
                <tr valign="top" style="x-cell-content-align: top">
                    <td colspan="1" rowspan="1" width="86">
                    </td>
                    <td align="center" colspan="1" rowspan="1" width="63">
                        100
                    </td>
                    <td colspan="1" rowspan="1" width="150">
                    </td>
                    <td align="center" colspan="1" rowspan="1" width="63">
                        80
                    </td>
                    <td colspan="1" rowspan="1" width="63">
                    </td>
                </tr>
                <tr valign="top" style="x-cell-content-align: top">
                    <td colspan="1" rowspan="1" width="86">
                    </td>
                    <td align="center" colspan="1" rowspan="1" width="63">
                        100
                    </td>
                    <td colspan="1" rowspan="1" width="150">
                    </td>
                    <td align="center" colspan="1" rowspan="1" width="63">
                        90
                    </td>
                    <td colspan="1" rowspan="1" width="63">
                    </td>
                </tr>
                <tr valign="top" style="x-cell-content-align: top">
                    <td colspan="1" rowspan="1" width="86">
                    </td>
                    <td align="center" colspan="1" rowspan="1" width="63">
                        101
                    </td>
                    <td colspan="1" rowspan="1" width="150">
                    </td>
                    <td align="center" colspan="1" rowspan="1" width="63">
                        90
                    </td>
                    <td colspan="1" rowspan="1" width="63">
                    </td>
                </tr>
                <tr valign="top" style="x-cell-content-align: top">
                    <td colspan="1" rowspan="1" width="86">
                    </td>
                    <td align="center" colspan="1" rowspan="1" width="63">
                        101
                    </td>
                    <td colspan="1" rowspan="1" width="150">
                    </td>
                    <td align="center" colspan="1" rowspan="1" width="63">
                        91
                    </td>
                    <td colspan="1" rowspan="1" width="51">
 </td>
                </tr>
            </tbody>
</table>
        <br />

/*This example shows the use of *LOVAL. The SETLL operation positions the file before the first record of a file in ascending order. The READ operation reads the first record (key value 97)./* 

```
DclFld NotFound *Ind        
DclFld ErrorOnSet *Ind
DclFld EndOfFile *Ind
SETLL PartMaster *LoVal Err (ErrorOnSet) NotFnd(NotFound)
If NotFound = *Off *And ErrorOnSet = *Off
    Read PartMaster Eof(EndOfFile)
Endif
```

/*This example shows the use of *HIVAL. The **SETGT** operation positions the file after the last record of a file in ascending order. The READP operation reads the last record (key value 91)./* 

```
DclFld NotFound *Ind
DclFld ErrorOnSet *Ind
DclFld EndOfFile *Ind
 **SETGT**  ItemMaster *HiVal Err (ErrorOnSet) NotFnd(NotFound)
If NotFound = *Off *And ErrorOnSet = *Off  
    ReadP ItemMaster Eof(EndOfFile)
Endif
```
        <br />
<table class="fineprint" id="Table4" style="WIDTH: 456px; border-spacing: 0px" cellspacing="0" width="456" x-use-null-cells="x-use-null-cells">
            <tr valign="top" style="x-cell-content-align: top">
                <td align="right" colspan="1" rowspan="1" width="86" style="height: 21px">
                </td>
                <td align="center" colspan="1" rowspan="1" width="63" style="height: 21px">
 **key<br />
                        field<br />
                        Values** 
                </td>
                <td colspan="1" rowspan="1" width="114" style="height: 21px">
                </td>
                <td align="center" colspan="1" rowspan="1" width="63" style="height: 21px">
 **key<br />
                        field<br />
                        Values** 
                </td>
                <td colspan="1" rowspan="1" style="height: 21px; width: 98px">
                </td>
            </tr>
            <tr valign="top" style="x-cell-content-align: top">
                <td colspan="1" rowspan="1" width="86">
 (SetLL) (Read)
                </td>
                <td align="center" colspan="1" rowspan="1" width="63">
                    97
                </td>
                <td colspan="1" rowspan="1" width="114">
                </td>
                <td align="center" colspan="1" rowspan="1" width="63">
                    50
                </td>
                <td colspan="1" rowspan="1" style="width: 98px" />
            </tr>
            <tr valign="top" style="x-cell-content-align: top">
                <td colspan="1" rowspan="1" width="86" />
                <td align="center" colspan="1" rowspan="1" width="63">
                    97
                </td>
                <td colspan="1" rowspan="1" width="114" />
                <td align="center" colspan="1" rowspan="1" width="63">
                    60
                </td>
                <td colspan="1" rowspan="1" style="width: 98px">
                </td>
            </tr>
            <tr valign="top" style="x-cell-content-align: top">
                <td colspan="1" rowspan="1" width="86">
                </td>
                <td align="center" colspan="1" rowspan="1" width="63">
                    97
                </td>
                <td colspan="1" rowspan="1" width="114">
                </td>
                <td align="center" colspan="1" rowspan="1" width="63">
                    70
                </td>
                <td colspan="1" rowspan="1" style="width: 98px">
                </td>
            </tr>
            <tr valign="top" style="x-cell-content-align: top">
                <td colspan="1" rowspan="1" width="86">
                </td>
                <td align="center" colspan="1" rowspan="1" width="63">
                    97
                </td>
                <td align="right" colspan="1" rowspan="1" width="114">
                </td>
                <td align="center" colspan="1" rowspan="1" width="63">
                    70
                </td>
                <td colspan="1" rowspan="1" style="width: 98px">
                </td>
            </tr>
            <tr valign="top" style="x-cell-content-align: top">
                <td colspan="1" rowspan="1" width="86">
                </td>
                <td align="center" colspan="1" rowspan="1" width="63">
                    98
                </td>
                <td colspan="1" rowspan="1" width="114">
                    PARTRECORD<br />
                    record format
                </td>
                <td align="center" colspan="1" rowspan="1" width="63">
                    80
                </td>
                <td colspan="1" rowspan="1" style="width: 98px">
                    ITEMRECORD<br />
                    record format
                </td>
            </tr>
            <tr valign="top" style="x-cell-content-align: top">
                <td align="right" colspan="1" rowspan="1" width="86">
                </td>
                <td align="center" colspan="1" rowspan="1" width="63">
                    100
                </td>
                <td colspan="1" rowspan="1" width="114">
                </td>
                <td align="center" colspan="1" rowspan="1" width="63">
                    80
                </td>
                <td colspan="1" rowspan="1" style="width: 98px">
                </td>
            </tr>
            <tr valign="top" style="x-cell-content-align: top">
                <td colspan="1" rowspan="1" width="86">
                </td>
                <td align="center" colspan="1" rowspan="1" width="63">
                    100
                </td>
                <td colspan="1" rowspan="1" width="114">
                </td>
                <td align="center" colspan="1" rowspan="1" width="63">
                    80
                </td>
                <td colspan="1" rowspan="1" style="width: 98px">
                </td>
            </tr>
            <tr valign="top" style="x-cell-content-align: top">
                <td colspan="1" rowspan="1" width="86">
                </td>
                <td align="center" colspan="1" rowspan="1" width="63">
                    100
                </td>
                <td colspan="1" rowspan="1" width="114">
                </td>
                <td align="center" colspan="1" rowspan="1" width="63">
                    90
                </td>
                <td colspan="1" rowspan="1" style="width: 98px">
                </td>
            </tr>
            <tr valign="top" style="x-cell-content-align: top">
                <td colspan="1" rowspan="1" width="86">
                </td>
                <td align="center" colspan="1" rowspan="1" width="63">
                    101
                </td>
                <td colspan="1" rowspan="1" width="114">
                </td>
                <td align="center" colspan="1" rowspan="1" width="63">
                    90
                </td>
                <td colspan="1" rowspan="1" style="width: 98px">
                </td>
            </tr>
            <tr valign="top" style="x-cell-content-align: top">
                <td colspan="1" rowspan="1" width="86">
                </td>
                <td align="center" colspan="1" rowspan="1" width="63">
                    101
                </td>
                <td align="right" colspan="1" rowspan="1" width="114">(READP)<br /> (SETGT) </td>
                <td align="center" colspan="1" rowspan="1" width="63">
                    91
                </td>
                <td colspan="1" rowspan="1" style="width: 98px"></td>
            </tr>
</table>
        <br />

### See Also
[*HIVAL](STARHIVAL.html)

[*LOVAL](STARLOVAL.html)

[CHAIN](CHAIN.html)

[Figurative Constants](Figurative_Constants.html)

[SETLL](SETLL.html)

[%KDS](KDS_Function.html) 

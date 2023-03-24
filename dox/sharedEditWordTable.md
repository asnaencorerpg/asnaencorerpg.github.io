---
title: Edit Word Usage

Id: sharedEditWordTable
TocParent: aerLrfEditWordTable
TocOrder: 10


---

Using an **EditWord** allows you to directly specify: 

- Blanks
- Output of the negative sign
- Suppression of unwanted zeroes
- Commas and decimal points
- Named Constants

At design-time, the edit word is not to be surrounded by an apostrophe. 

**For example:** 

```
Use EditWord: 0 *bbb-bbb-bbbb* 
Not EditWord: "0 *bbb-bbb-bbbb"* 
```
**<span style="COLOR:navy"> The Edit Word is basically divided into three parts: </span>** 

1. The ** *Body* **  is the area for the digits transferred from the source data field to the output
                record.  The body begins at the left most position of the edit word. 
                The number of blanks, plus one zero or an asterisk in the edit word body must
                be equal to or greater than the number of digits of the source data field to be
                edited.  The body ends with the rightmost character that can be replaced
                by a digit.
2. The ** *Status* **  follows the last blank in the edit word, if
                used.  It defines a space for a negative indicator, either a minus sign,
                or the two letters **CR** .  The negative indicator will display
                only if the source data is negative.  If the source data is positive, the
                status positions are replaced by blanks.  Edit words without the CR or -
                indicators have no status positions.  If more than one CR follows the last
                blank, the first CR is treated as a status, and the remaining CR’s are treated
                as constants.  The minus sign must be the last character in the edit word.
3. The ** *Expansion* **  is entered after the **Status**  and consists of
                a series of ampersands and constant characters.  Ampersands are replaced
                by blank spaces in the output.  Constants are output as is and follows the
                body, if status is not specified.

**<span style="COLOR:navy">The Body</span>** 

**Blank:** Blank is replaced with the character from the corresponding position of the Source Data field. 

**Decimals and Commas:** Decimals and commas are in the same relative position in the edited output field as they are in the edit word unless they appear to the left of the first significant digit in the edit word. In that case, they are blanked out or replaced by an asterisk. 

In the following examples, all the leading zeros will be suppressed (default) and the decimal point will not print unless there is a significant digit to its left. 

<table class="dtTABLE" id="Table13" cellspacing="0">
                    <colgroup span="1">
                        <col align="middles" span="1" width="33%" style="FONT-WEIGHT: bold" />
                        <col span="1" width="33%" />
                        <col span="1" width="33%" />
                    </colgroup>
                    <tr>
                        <th colspan="1" rowspan="1">Edit Word</th>
                        <th colspan="1" rowspan="1">Source Data</th>
                        <th colspan="1" rowspan="1">Appears as:</th>
                    </tr>
                    <tr>
                        <td colspan="1" rowspan="1">bbbbbbb</td>
                        <td colspan="1" rowspan="1">0000052</td>
                        <td colspan="1" rowspan="1">bbbbb52</td>
                    </tr>
                    <tr>
                        <td colspan="1" rowspan="1">bbbbbbb.bb</td>
                        <td colspan="1" rowspan="1">000000099</td>
                        <td colspan="1" rowspan="1">bbbbbbbb99</td>
                    </tr>
                    <tr>
                        <td colspan="1" rowspan="1">bbbbbbb.bb</td>
                        <td colspan="1" rowspan="1">000000542</td>
                        <td colspan="1" rowspan="1">bbbbbb5.42</td>
                    </tr>
</table>


**Zeros:** The first zero in the **body** of the edit word is interpreted as an end-zero-suppression character. This zero is placed where zero suppression is to end. Subsequent zeros put into the edit word are treated as constants (see "Constants" below). Any leading zeros in the Source Data are suppressed up to and including the position of the end-zero-suppression character. Significant digits that would appear in the end-zero-suppression character position, or to the left of it, are output. 

<table class="dtTABLE" id="Table2" cellspacing="0">
                    <colgroup span="1">
                        <col align="middles" span="1" style="FONT-WEIGHT: bold" width="33%" />
                        <col span="1" width="33%" />
                        <col span="1" width="33%" />
                    </colgroup>
                    <tr>
                        <th colspan="1" rowspan="1">
                            Edit Word
                        </th>
                        <th colspan="1" rowspan="1">
                            Source Data
                        </th>
                        <th colspan="1" rowspan="1">
                            Appears as:
                        </th>
                    </tr>
                    <tr>
                        <td colspan="1" rowspan="1">

bbb0bbbbbb
</td>
                        <td colspan="1" rowspan="1">

00000009
</td>
                        <td colspan="1" rowspan="1">

bbbb000009
</td>
                    </tr>
                    <tr>
                        <td colspan="1" rowspan="1">

bbb0bbbbbb
</td>
                        <td colspan="1" rowspan="1">

098745
</td>
                        <td colspan="1" rowspan="1">

bbbb098745
</td>
                    </tr>
                    <tr>
                        <td colspan="1" rowspan="1">

bbb0bbbbbb
</td>
                        <td colspan="1" rowspan="1">

098765432
</td>
                        <td colspan="1" rowspan="1">

bb98765432
</td>
                    </tr>
</table>


If the leading zeros include, or extend to the right of, the end-zero-suppression character position, that position is replaced with a blank. This means that if you wish the same number of leading zeros to appear in the output as exist in the Source Data, the edit word body must be wider than the Source Data. 

<table class="dtTABLE" id="Table3" cellspacing="0">
                    <colgroup span="1">
                        <col align="middles" span="1" style="FONT-WEIGHT: bold" width="33%" />
                        <col span="1" width="33%" />
                        <col span="1" width="33%" />
                    </colgroup>
                    <tr>
                        <th colspan="1" rowspan="1">
                            Edit Word
                        </th>
                        <th colspan="1" rowspan="1">
                            Source Data
                        </th>
                        <th colspan="1" rowspan="1">
                            Appears as:
                        </th>
                    </tr>
                    <tr>
                        <td colspan="1" rowspan="1">

0bbb
</td>
                        <td colspan="1" rowspan="1">

0541
</td>
                        <td colspan="1" rowspan="1">

b541
</td>
                    </tr>
                    <tr>
                        <td colspan="1" rowspan="1">

0bbbb
</td>
                        <td colspan="1" rowspan="1">

0541
</td>
                        <td colspan="1" rowspan="1">

b0541
</td>
                    </tr>
</table>


**Constants** (including commas and decimal point) that are placed to the right of the end-zero-suppression character are output, even if there is no Source Data. Constants to the left of the end-zero-suppression character are only output if the Source Data has significant digits that would be placed to the left of these constants. 

<table class="dtTABLE" id="Table4" cellspacing="0">
                    <colgroup span="1">
                        <col align="middles" span="1" style="FONT-WEIGHT: bold" width="33%" />
                        <col span="1" width="33%" />
                        <col span="1" width="33%" />
                    </colgroup>
                    <tr>
                        <th colspan="1" rowspan="1">
                            Edit Word
                        </th>
                        <th colspan="1" rowspan="1">
                            Source Data
                        </th>
                        <th colspan="1" rowspan="1">
                            Appears as:
                        </th>
                    </tr>
                    <tr>
                        <td colspan="1" rowspan="1">

bbbbbb0.bb
</td>
                        <td colspan="1" rowspan="1">

000000008
</td>
                        <td colspan="1" rowspan="1">

bbbbbbb.08
</td>
                    </tr>
                    <tr>
                        <td colspan="1" rowspan="1">

bbbbbb0.bb
</td>
                        <td colspan="1" rowspan="1">

000000000
</td>
                        <td colspan="1" rowspan="1">

bbbbbbb.bb
</td>
                    </tr>
                    <tr>
                        <td colspan="1" rowspan="1">

bbb,b0b.bb
</td>
                        <td colspan="1" rowspan="1">

00000045
</td>
                        <td colspan="1" rowspan="1">

bbbbbb0.45
</td>
                    </tr>
                    <tr>
                        <td colspan="1" rowspan="1">

bbb,b0b.bb
</td>
                        <td colspan="1" rowspan="1">

00000854
</td>
                        <td colspan="1" rowspan="1">

bbbbbb8.54
</td>
                    </tr>
                    <tr>
                        <td colspan="1" rowspan="1">

b0b,bbb.bb
</td>
                        <td colspan="1" rowspan="1">

00000854
</td>
                        <td colspan="1" rowspan="1">

bb0,008.54
</td>
                    </tr>
                    <tr>
                        <td colspan="1" rowspan="1">

b,b0b,bbb.bb
</td>
                        <td colspan="1" rowspan="1">

000008545
</td>
                        <td colspan="1" rowspan="1">

bbb0,008.54
</td>
                    </tr>
</table>


**Asterisk:** The first asterisk in the body of an edit word also ends zero suppression. Subsequent asterisks put into the edit word are treated as constants (see "Constants" below). Any zeros in the edit word following this asterisk are also treated as constants. There can be only one end-zero-suppression character in an edit word, and that character is the first asterisk or the first zero in the edit word. If an asterisk is used as an end-zero-suppression character, all leading zeros that are suppressed are replaced with asterisks in the output. Otherwise, the asterisk suppresses leading zeros in the same way as described above for "Zeros". 

<table class="dtTABLE" id="Table5" cellspacing="0">
                <colgroup span="1">
                    <col align="middles" span="1" style="FONT-WEIGHT: bold" width="33%" />
                    <col span="1" width="33%" />
                    <col span="1" width="33%" />
                </colgroup>
                <tr>
                    <th colspan="1" rowspan="1">Edit Word</th>
                    <th colspan="1" rowspan="1">Source Data</th>
                    <th colspan="1" rowspan="1">Appears as:</th>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">*bbbbbb.bb</td>
                    <td colspan="1" rowspan="1">000000854</td>
                    <td colspan="1" rowspan="1">*bbbbb8.54</td> 
                </tr> 
                <tr> 
                    <td colspan="1" rowspan="1"> bbbbb*b.bb</td>
                    <td colspan="1" rowspan="1">000000125</td>
                    <td colspan="1" rowspan="1">******1.25</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">bbbbb*b.bb**</td>
                    <td colspan="1" rowspan="1">000074524</td>
                    <td colspan="1" rowspan="1">****745.24**</td>
                </tr>
</table>

Note that leading zeros appearing after the asterisk position are output as leading zeros. Only the suppressed leading zeros, including the one in the asterisk position, are replaced by asterisks. 

**Currency Symbol:** A currency symbol followed directly by a first zero in the edit word (end-zero-suppression character) is said to float. All leading zeros are suppressed in the output and the currency symbol appears in the output immediately to the left of the most significant digit. 

<table class="dtTABLE" id="Table6" cellspacing="0">
                <colgroup span="1">
                    <col align="middles" span="1" style="FONT-WEIGHT: bold" width="33%" />
                    <col span="1" width="33%" />
                    <col span="1" width="33%" />
                </colgroup>
                <tr>
                    <th colspan="1" rowspan="1">Edit Word</th>
                    <th colspan="1" rowspan="1">Source Data</th>
                    <th colspan="1" rowspan="1">Appears as:</th>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">bb,bbb,b$0.bb</td>
                    <td colspan="1" rowspan="1">000000125</td>
                    <td colspan="1" rowspan="1">bbbbbbbbb$1.25</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">bb,bbb,b$0.bb</td>
                    <td colspan="1" rowspan="1">000841458</td>
                    <td colspan="1" rowspan="1">bbbb$8,414.58</td>
                </tr>
</table>


If the currency symbol is put into the first position of the edit word, then it will always appear in that position in the output. This is called a fixed currency symbol. 


<table class="dtTABLE" id="Table7" cellspacing="0">
                <colgroup span="1">
                    <col align="middles" span="1" style="FONT-WEIGHT: bold" width="33%" />
                    <col span="1" width="33%" />
                    <col span="1" width="33%" />
                </colgroup>
                <tr>
                    <th colspan="1" rowspan="1">
                        Edit Word
                    </th>
                    <th colspan="1" rowspan="1">
                        Source Data
                    </th>
                    <th colspan="1" rowspan="1">
                        Appears as:
                    </th>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

$b,bbb,bb0.bb
</td>
                    <td colspan="1" rowspan="1">

000854174
</td>
                    <td colspan="1" rowspan="1">

$bbbb8,541.74
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

$bb,bbb,0b0.bb
</td>
                    <td colspan="1" rowspan="1">

000000000
</td>
                    <td colspan="1" rowspan="1">

$bbbbbb00.00
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

$b,bbb,*bb.bb
</td>
                    <td colspan="1" rowspan="1">

000745478
</td>
                    <td colspan="1" rowspan="1">

$****7,454.78
</td>
                </tr>
</table>

A currency symbol anywhere else in the edit word and not immediately followed by a zero end-suppression-character is treated as a constant (see "Constants" below). 

**Ampersand:** Creates a blank in the edited field. The examples below might be used to edit a telephone number. Note that the zero in the first position is required to print the constant AREA. 


<table class="dtTABLE" id="Table8" cellspacing="0">
                <colgroup span="1">
                    <col align="middles" span="1" style="FONT-WEIGHT: bold" width="33%" />
                    <col span="1" width="33%" />
                    <col span="1" width="33%" />
                </colgroup>
                <tr>
                    <th colspan="1" rowspan="1">
                        Edit Word
                    </th>
                    <th colspan="1" rowspan="1">
                        Source Data
                    </th>
                    <th colspan="1" rowspan="1">
                        Appears as:
                    </th>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

0Area&bbb&No.&bbb-bbbb
</td>
                    <td colspan="1" rowspan="1">

9413784307
</td>
                    <td colspan="1" rowspan="1">

Area 941 No. 378-4307

</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

0Area&[bbb]&No.&bbb-bbbb
</td>
                    <td colspan="1" rowspan="1">

9413784307
</td>
                    <td colspan="1" rowspan="1">

Area [941] No. 378-4307
</td>
                </tr>
</table>


**Constants:** All other characters entered into the body of the edit word re treated as constants. If the Source Data is such that the output places significant digits or leading zeros to the left of any constant, then that constant appears in the output. Otherwise, the constant is suppressed in the output. Commas and the decimal point follow the same rules as for constants. Notice in the examples below, that the presence of the end-zero-suppression character as well as the number of significant digits in the Source Data, influence the output of constants. 

The following edit words could be used to print checks. *Note that the second asterisk is treated as a constant, and that, in the third example, the constants preceding the first significant digit are not output.* 

<table class="dtTABLE" id="Table9" cellspacing="0">
                <colgroup span="1">
                    <col align="middles" span="1" style="FONT-WEIGHT: bold" width="33%" />
                    <col span="1" width="33%" />
                    <col span="1" width="33%" />
                </colgroup>
                <tr>
                    <th colspan="1" rowspan="1">
                        Edit Word
                    </th>
                    <th colspan="1" rowspan="1">
                        Source Data
                    </th>
                    <th colspan="1" rowspan="1">
                        Appears as:
                    </th>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

$bbbbbb**Dollars&bb&Cts
</td>
                    <td colspan="1" rowspan="1">

000085474
</td>
                    <td colspan="1" rowspan="1">

$****854*Dollars 74 Cts
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

$bbbbbb**Dollars&bb&Cts
</td>
                    <td colspan="1" rowspan="1">

000000010
</td>
                    <td colspan="1" rowspan="1">

$********Dollars 10 Cts
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

$bbbbbbb&Dollars&bb&Cts
</td>
                    <td colspan="1" rowspan="1">

000000010
</td>
                    <td colspan="1" rowspan="1">

$ 10 Cts
</td>
                </tr>
</table>


A date could be printed by using either edit word:

<table class="dtTABLE" id="Table10" cellspacing="0">
                <colgroup span="1">
                    <col align="middles" span="1" style="FONT-WEIGHT: bold" width="33%" />
                    <col span="1" width="33%" />
                    <col span="1" width="33%" />
                </colgroup>
                <tr>
                    <th colspan="1" rowspan="1">
                        Edit Word
                    </th>
                    <th colspan="1" rowspan="1">
                        Source Data
                    </th>
                    <th colspan="1" rowspan="1">
                        Appears as:
                    </th>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

bb/bb/bb
</td>
                    <td colspan="1" rowspan="1">

072396
</td>
                    <td colspan="1" rowspan="1">

7/23/96
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

0bb/bb/bb
</td>
                    <td colspan="1" rowspan="1">

072396
</td>
                    <td colspan="1" rowspan="1">

07/23/96
</td>
                </tr>
</table>
            

Note that any zeros or asterisks following the first occurrence of an edit word are treated as constants. The same is true for - and CR. 

<table class="dtTABLE" id="Table11" cellspacing="0">
                <colgroup span="1">
                    <col align="middles" span="1" style="FONT-WEIGHT: bold" width="33%" />
                    <col span="1" width="33%" />
                    <col span="1" width="33%" />
                </colgroup>
                <tr>
                    <th colspan="1" rowspan="1">
                        Edit Word
                    </th>
                    <th colspan="1" rowspan="1">
                        Source Data
                    </th>
                    <th colspan="1" rowspan="1">
                        Appears as:
                    </th>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

bb0.bb000
</td>
                    <td colspan="1" rowspan="1">

08541
</td>
                    <td colspan="1" rowspan="1">

85.41000
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

bb*.bb000
</td>
                    <td colspan="1" rowspan="1">

08541
</td>
                    <td colspan="1" rowspan="1">

*85.41000
</td>
                </tr>
</table>

**The Status** 

The following characters have special meanings within the status:

**Ampersand** - Causes a blank in the edited output field. An ampersand can not be placed in the edited output field. 

**CR or - symbol** - If the sign in the edited output is a plus (+), these positions are blanked out. If the sign in the edited output field is a minus (-), these positions remain undisturbed. The minus sign will only print when the field value is negative. 

**The Expansion** 

The characters in this position are always displayed. This area can **not** contain blanks. If a blank is required in the edited output field, specify an ampersand in the body of the edit word. 

### See Also
[Edit Code Table](sharedEditCodeTable.html)  

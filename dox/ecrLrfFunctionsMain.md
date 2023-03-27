---
title: Functions

Id: aerLrfFunctionsMain
TocParent: aerLrfLangElementsMain
TocOrder: 70


---

Encore RPG **built-in functions** are similar to RPG operation codes in that they provide an action that returns a result. However, built-in functions can be used in expressions. (eg, x = %XFOOT( MyArray ) ). Built-in functions always start with a percent sign ( **%** ). 

### Usage
<pre class="syntax">
 **function-name{(argument{:argument...})}** 
- or -
 **function-name{(argument{,argument...})}** </pre>

As defined by IBM, built-in functions use a colon ( **:** ) to delimit arguments being passed to a function. For example, the formal IBM syntax for using the %EDITC function is: 
<pre class="OH_CodeSnippetContainerCode">    x = %EDITC( NumVal : "3" )</pre>

where the colon delimits the functions arguments.

Encore RPG offers an optional, more intuitive syntax, that uses the comma( **,** ) to separate function arguments. For example, 
<pre class="OH_CodeSnippetContainerCode">    x = %EDITC( NumVal, "3" )</pre>

is also valid with Encore RPG code.

**You can use whichever syntax you prefer.** 

Arguments for the function may be variables, constants, expressions, a prototyped procedure, or other built-in functions. An expression argument can include a built-in function. 

See the individual built-in function descriptions for details on what arguments are allowed. 
<br />

<table class="dtTABLE" id="Table3" style="x-cell-content-align: Top; border-spacing: 0px" cellspacing="0" x-use-null-cells="x-use-null-cells">
                <colgroup span="1" class="normal">
                    <col span="1" valign="top" width="10%" />
                    <col span="1" valign="top" width="39.99%" />
                    <col span="1" valign="top" width="45%" />
                </colgroup>
                <tr>
                    <th colspan="1" rowspan="1">
                        Built-In Function
                    </th>
                    <th colspan="1" rowspan="1">
                        Argument(s)
                    </th>
                    <th colspan="1" rowspan="1">
                        Value Returned
                    </th>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%ABS](ABS_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

numeric expression 
</td>
                    <td colspan="1" rowspan="1">

Absolute value of the numeric expression. 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%BOOL](ABS_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

boolean expression
</td>
                    <td colspan="1" rowspan="1">

True of False value.
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%CHAR](CHAR_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

numeric, date, time or timestamp expression 
</td>
                    <td colspan="1" rowspan="1">

Value in character format. 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%CHECK](CHECK_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

comparator, base {,start} 
</td>
                    <td colspan="1" rowspan="1">

The first position of *base* ( *start* , then left to right) that contains acharacter that does NOT appear in *comparator* : otherwise 0. *start* default is 1. 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%CHECKR](CHECKR_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

comparator, base {,start} 
</td>
                    <td colspan="1" rowspan="1">

The last position of *base* ( *start* , then right to left) that contains acharacter that does NOT appear in *comparator* : otherwise 0. *start* default is the length of the string. 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%DATE](DATE_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

(character, numeric, or timestamp expression {,*ISO *JUL | *USa| *EUR | *JIS | *MDY | *DMY | *YMD}) 
</td>
                    <td colspan="1" rowspan="1">

Value of expression converted to type date or the current system date in *ISO date format.
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%DAYS](DAYS_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

number 
</td>
                    <td colspan="1" rowspan="1">

The result is a date or timestamp value with the appropriate *number* of days added or subtracted.
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%DEC](DEC_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

numeric expression { **,** digits **,** decpos } 
</td>
                    <td colspan="1" rowspan="1">

Value in packed numeric format. 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%DECH](DECH_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

numeric expression,digits, decpos 
</td>
                    <td colspan="1" rowspan="1">

Half-adjusted value in packed numeric format. 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%DECPOS](DECPOS_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

numeric expression 
</td>
                    <td colspan="1" rowspan="1">

Number of decimal digits. 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%DIFF](DIFF_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

op1, op2, {*MSECONDS | *SECONDS | *MINUTES | *HOURS | *DAYS | *MONTHS | *YEARS} 
</td>
                    <td colspan="1" rowspan="1">

The difference (duration) between two date, time, or timestamp values. 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%DIGITS](Digits_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

Numeric **,** start{ **,** length} 
</td>
                    <td colspan="1" rowspan="1">

Value in integer format.
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%DIV](DIV_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

dividend **,** divisor 
</td>
                    <td colspan="1" rowspan="1">

The quotient from the division of two arguments; packed numeric if either operand is a packed, zoned, or binary numeric value, or integer if either operand is an integer numeric value. 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%EDITC](EDITC_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

non-float numeric expression **,** edit code { **,** *ASTFill | *CURSYM | currency-symbol})
</td>
                    <td colspan="1" rowspan="1">

Value in string format representing the edited value. 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%EDITFLT](EDITFLT_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

numeric expression 
</td>
                    <td colspan="1" rowspan="1">

Character external display representation of float. 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%EDITW](EDITW_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

non-float numeric expression **,** edit word 
</td>
                    <td colspan="1" rowspan="1">

Value in string format representing the edited value. 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1" style="height: 47px">

[%ELEM](ELEM_Function.html) 
</td>
                    <td colspan="1" rowspan="1" style="height: 47px">

array, table, or multiple occurrence datastructure name 
</td>
                    <td colspan="1" rowspan="1" style="height: 47px">

Number of elements or occurrences. 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%EOF](EOF_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

{file name} 
</td>
                    <td colspan="1" rowspan="1">

"1" if the most recent read operation or write to a subfile ended in an end of file or beginning of file condition; otherwise, it returns "0". 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%EQUAL](EQUAL_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

{file name} 
</td>
                    <td colspan="1" rowspan="1">

"1" if the most recent relevant operation found an exact match; otherwise, it returns "0". 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%ERROR](ERROR_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

</td> <td colspan="1" rowspan="1"> <p> "1" if the most recent operation with extender "E" specified resulted in an error condition. "0" and remains unchanged following the operation if no error occurs. 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%FLOAT](FLOAT_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

numeric expression 
</td>
                    <td colspan="1" rowspan="1">

Value in float format. 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%FOUND](FOUND_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

{file name} 
</td>
                    <td colspan="1" rowspan="1">

"1" if the most recent relevant file operation found a record (CHAIN, DELETE, SETGT, SETLL), an element (LOOKUP), or a match (CHECK, CHECKR, SCAN). Otherwise, this function returns "0". 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%HOURS](HOURS_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

number 
</td>
                    <td colspan="1" rowspan="1">

The result is a time or timestamp value with the appropriate *number* of hours added or subtracted. 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%INT](INT_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

numeric expression 
</td>
                    <td colspan="1" rowspan="1">

Value in integer format. 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%INTH](INTH_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

numeric expression 
</td>
                    <td colspan="1" rowspan="1">

**Half-adjusted** value in integer format. 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%KDS](KDS_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

dsn name {,number-keys} 
</td>
                    <td colspan="1" rowspan="1">

The datastructure reference as indicated by setting the *Key* parameter in the [CHAIN](CHAIN.html), [DELETE](DELETE.html), [READE](READE.html), [READPE](READPE.html), [SETGT](SETGT.html), or [SETLL](SETLL.html) using this function. 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%LEN](LEN_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

expression 
</td>
                    <td colspan="1" rowspan="1">

The length of a program defined variable or database variable defined as variable length, or also the current length of such fields. 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%LOOKUP](LOOKUP_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

argument, array {,start-index {,num-elements}} 
</td>
                    <td colspan="1" rowspan="1">

Returns the array index of the item in *array* that matches the *argument* ; otherwise, zero if no match is found. 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%MINUTES](MINUTES_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

number 
</td>
                    <td colspan="1" rowspan="1">

The result is a time or timestamp value with the appropriate *number* of minutes added or subtracted.
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%MONTHS](MONTHS_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

number 
</td>
                    <td colspan="1" rowspan="1">

The result is a date or timestamp value with the appropriate *number* of months added or subtracted.
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%MSECONDS](MSECONDS_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

number 
</td>
                    <td colspan="1" rowspan="1">

The result is a time or timestamp value with the appropriate *number* of microseconds added or subtracted. 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%NULLIND](NULLIND_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

fieldname 
</td>
                    <td colspan="1" rowspan="1">

The name of the field to query or set the null indicator for null-capable fields. 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%OCCUR](OCCUR_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

dsn name 
</td>
                    <td colspan="1" rowspan="1">

Returns an unsigned numeric value of the current occurrence number of the dsn name (datastructure). Also can be used to set the occurrence number. 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%OMITTED](OMITTED_Function.html) 
</td>
                    <td colspan="1" rowspan="1" />
                    <td colspan="1" rowspan="1">

%OMITTED is **only** valid inside of BegProc routines for ILE procedures, and is only valid on Parameters that have the * **OMIT** option; i.e. 

DCLSRPARM CustName Options (*OMIT) 

if not %OMITTED(CustName) 

// we have aname 

EndIf 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%OPEN](OPEN_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

file name 
</td>
                    <td colspan="1" rowspan="1">

"1" if the specified file is open.<br /> "0" if the specified file is closed. 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%PARMS](PARMS_Function.html) 
</td>
                    <td colspan="1" rowspan="1">number</td>
                    <td colspan="1" rowspan="1">

%Parms is **only** valid inside of BegProc routines for ILE procedures.

DCLSRPARM CustName Options(*OMIT)<br />DCLSRPARM CustAddress<br />DCLSRPARM CustPhone Options(*Omit, *NoPass) 

If (%Parms = 3)

// if we are here, it means that CustPone was passed, but it may be omitted 

If not %OMITTED(CustPhone)

// we have a valid phone number 

EndIf

EndIf 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%REM](REM_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

**,** dividend **,** divisor 
</td>
                    <td colspan="1" rowspan="1">

The remainder from the division of the two arguments. 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%REPLACE](REPLACE_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

Replacement string , source string { **,** start position{ **,** source length to Replace}} 
</td>
                    <td colspan="1" rowspan="1">

String produced by inserting Replacement string into source string, starting at start position and replacing the specified number of characters. 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%SCAN](SCAN_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

Search argument **,** string to be searched { **,** start position] 
</td>
                    <td colspan="1" rowspan="1">

First position of search argument in string, or zero if not found. 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%SECONDS](SECONDS_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

number 
</td>
                    <td colspan="1" rowspan="1">

The result is a time or timestamp value with the appropriate *number* of seconds added or subtracted. 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%SQRT](SQRT_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

numeric expression 
</td>
                    <td colspan="1" rowspan="1">

The square root of the numeric expression.
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%SUBDT](SUBDT_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

date, time, or timestamp value, {*MSECONDS | *SECONDS | *MINUTES | *HOURS | *DAYS | *MONTHS | *YEARS} 
</td>
                    <td colspan="1" rowspan="1">

An unsigned numeric value with the extracted portion of a date, time, or timestamp value. 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%SUBST](SUBST_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

String **,** start{ **,** length} 
</td>
                    <td colspan="1" rowspan="1">

Substring.
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%TIME](TIME_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

(character, numeric, or timestamp expression {, *ISO | *HMS | *USa| *EUR | *JIS})
</td>
                    <td colspan="1" rowspan="1">

Value of expression converted to type time or the current system time in *ISO format.
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%TIMESTAMP](TIMESTAMP_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

(character, numeric, or timestamp expression {, *ISO | *ISO0})
</td>
                    <td colspan="1" rowspan="1">

Value of expression converted to type timestamp or the current system timestamp in *ISO format.
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%TLOOKUP](TLOOKUP_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

argument, search-table {, alternate_table} 
</td>
                    <td colspan="1" rowspan="1">

Sets the current table element to the element that satisfies the condition and returns the value ***ON** , otherwise, ***OFF** if no match is found. 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%TRIM](TRIM_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

string 
</td>
                    <td colspan="1" rowspan="1">

String with **left** and **right** blanks trimmed. 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%TRIML](TRIML_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

string 
</td>
                    <td colspan="1" rowspan="1">

String with **left** blanks trimmed. 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%TRIMR](TRIMR_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

string 
</td>
                    <td colspan="1" rowspan="1">

String with **right** blanks trimmed. 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%XFOOT](XFOOT_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

array expression 
</td>
                    <td colspan="1" rowspan="1">

Sum of the elements. 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%XLATE](XLATE_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

from, to, string {,start position} 
</td>
                    <td colspan="1" rowspan="1">

Value translated from *String* , with any *From* character values replaced with the corresponding *To* character values. 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[%YEARS](YEARS_Function.html) 
</td>
                    <td colspan="1" rowspan="1">

number 
</td>
                    <td colspan="1" rowspan="1">

The result is a date or timestamp value with the appropriate *number* of years added or subtracted.
</td>
                </tr>
</table>

### Related Sections
[Encore RPG Language Reference](ecrLrfLangRefMain.html) <br /> Provides a reference of the Encore RPG language. 

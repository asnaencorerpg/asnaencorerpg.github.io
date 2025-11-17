---
title: Built-In Functions

Id: Functions_overview
TocParent: aerLrfLangRefMain
TocOrder: 0


---

Encore RPG **built-in functions** are similar to RPG operation codes in that they provide an action that returns a result. However, built-in functions can be used in expressions). (eg, x = %XFOOT( MyArray ) ). Built-in functions always start with a percent sign ( **%** ). 

### Usage

**function-name{(argument{:argument...})}** 

    - or -

 **function-name{(argument{,argument...})}** 


As defined by IBM, built-in functions use a colon ( **:** ) to delimit arguments being passed to a function. For example, the formal IBM syntax for using the %EDITC function is: 

```
    x = %EDITC( NumVal : "3" )
```

where the colon delimits the functions arguments.

Encore RPG offers an optional, more intuitive syntax, that uses the comma ( **,** ) to separate function arguments. For example, 

```
    x = %EDITC( NumVal, "3" )
```

is also valid with Encore RPG code.

**You can use whichever syntax you prefer.** 

Arguments for the function may be variables, constants, expressions, a prototyped procedure, or other built-in functions. An expression argument can include a built-in function. 

**Note** – In syntax samples and elsewhere, optional arguments are surrounded by curly braces ({}). These braces are not used in actual code, they only serve as a visual indicator that an argument is optional. 

See the individual built-in function descriptions for details on what arguments are allowed. 
<br />

| Built-In Function | Argument(s) | Value Returned |
| --- | --- | --- |
| [%ABS](ABS_Function.html) | numeric expression | Absolute value of the numeric expression. |
| [%BOOL](BOOL_Function.html) | boolean expression | True or False value. |
| [%CHAR](CHAR_Function.html) | numeric, date, time or timestamp expression | Value in character format. |
| [%CHECK](CHECK_Function.html) | comparator, base {, start} | The first position of base (start, then left to right) that contains a character that does NOT appear in comparator; otherwise 0. start default is 1. |
| [%CHECKR](CHECKR_Function.html) | comparator, base {, start} | The last position of base (start, then right to left) that contains a character that does NOT appear in comparator; otherwise 0. start default is the length of the string. |
| [%DATE](DATE_Function.html) | (character, numeric, or timestamp expression {, *ISO \| *JUL \| *USA \| *EUR \| *JIS \| *MDY \| *DMY \| *YMD}) | Value of expression converted to type date or the current system date in ISO date format. |
| [%DAYS](DAYS_Function.html) | number | A date or timestamp value with the appropriate number of days added or subtracted. |
| [%DEC](DEC_Function.html) | numeric expression {, digits, decpos} | Value in packed numeric format. |
| [%DECH](DECH_Function.html) | numeric expression, digits, decpos | Half-adjusted value in packed numeric format. |
| [%DECPOS](DECPOS_Function.html) | numeric expression | Number of decimal digits. |
| [%DIFF](DIFF_Function.html) | op1, op2, { *MSECONDS \| *SECONDS \| *MINUTES \| *HOURS \| *DAYS \| *MONTHS \| *YEARS } | The difference (duration) between two date, time, or timestamp values. |
| [%DIGITS](Digits_Function.html) | Numeric, start {, length} | Value in integer format. |
| [%DIV](DIV_Function.html) | dividend, divisor | The quotient from the division of two arguments; packed numeric if either operand is a packed, zoned, or binary numeric value, or integer if either operand is an integer numeric value. |
| [%EDITC](EDITC_Function.html) | non-float numeric expression, edit code {, *ASTFill \| *CURSYM \| currency-symbol} | Value in string format representing the edited value. |
| [%EDITFLT](EDITFLT_Function.html) | numeric expression | Character external display representation of float. |
| [%EDITW](EDITW_Function.html) | non-float numeric expression, edit word | Value in string format representing the edited value. |
| [%ELEM](ELEM_Function.html) | array, table, or multiple occurrence data structure name | Number of elements or occurrences. |
| [%EOF](EOF_Function.html) | {file name} | "1" if the most recent read operation or write to a subfile ended in an end of file or beginning of file condition; otherwise, "0". |
| [%EQUAL](EQUAL_Function.html) | {file name} | "1" if the most recent relevant operation found an exact match; otherwise, "0". |
| [%ERROR](ERROR_Function.html) |  | "1" if the most recent operation with extender "E" specified resulted in an error condition; "0" and remains unchanged following the operation if no error occurs. |
| [%FLOAT](FLOAT_Function.html) | numeric expression | Value in float format. |
| [%FOUND](FOUND_Function.html) | {file name} | "1" if the most recent relevant file operation found a record (CHAIN, DELETE, SETGT, SETLL), an element (LOOKUP), or a match (CHECK, CHECKR, SCAN); otherwise, "0". |
| [%HOURS](HOURS_Function.html) | number | A time or timestamp value with the appropriate number of hours added or subtracted. |
| [%INT](INT_Function.html) | numeric expression | Value in integer format. |
| [%INTH](INTH_Function.html) | numeric expression | Half-adjusted value in integer format. |
| [%KDS](KDS_Function.html) | dsn name {, number-keys} | The data structure reference as indicated by setting the Key parameter in the [CHAIN](CHAIN.html), [DELETE](DELETE.html), [READE](READE.html), [READPE](READPE.html), [SETGT](SETGT.html), or [SETLL](SETLL.html) using this function. |
| [%LEN](LEN_Function.html) | expression | The length of a program-defined variable or database variable defined as variable length, or the current length of such fields. |
| [%LOOKUP](LOOKUP_Function.html) | argument, array {, start-index {, num-elements}} | Returns the array index of the item in array that matches the argument; otherwise, zero if no match is found. |
| [%MINUTES](MINUTES_Function.html) | number | A time or timestamp value with the appropriate number of minutes added or subtracted. |
| [%MONTHS](MONTHS_Function.html) | number | A date or timestamp value with the appropriate number of months added or subtracted. |
| [%MSECONDS](MSECONDS_Function.html) | number | A time or timestamp value with the appropriate number of microseconds added or subtracted. |
| [%NULLIND](NULLIND_Function.html) | fieldname | The name of the field to query or set the null indicator for null-capable fields. |
| [%OCCUR](OCCUR_Function.html) | dsn name | Returns an unsigned numeric value of the current occurrence number of the dsn name (data structure). Also can be used to set the occurrence number. |
| [%OMITTED](OMITTED_Function.html) |  | %OMITTED is only valid inside BegProc routines for ILE procedures, and only on parameters with the OMIt option. Example:<br/> DCLSRPARM CustName Options(*OMIT)<br/> if not %OMITTED(CustName)<br/> // we have a name<br/> EndIf |
| [%OPEN](OPEN_Function.html) | file name | "1" if the specified file is open; "0" if the specified file is closed. |
| [%PARMS](PARMS_Function.html) |  | Number of parameters passed to the BegProc routine. Example:<br/> DCLSRPARM CustName Options(*OMIT)<br/> DCLSRPARM CustAddress<br/> DCLSRPARM CustPhone Options(*Omit, *NoPass)<br/><br/> If (%Parms = 3)<br/> // CustPhone was passed (it may be omitted)<br/>   If not %OMITTED(CustPhone)<br/>   // we have a valid phone number<br/>   EndIf<br/> EndIf |
| [%REM](REM_Function.html) | dividend, divisor | The remainder from the division of the two arguments. |
| [%REPLACE](REPLACE_Function.html) | Replacement string, source string {, start position {, source length to replace}} | String produced by inserting Replacement string into source string, starting at start position and replacing the specified number of characters. |
| [%SCAN](SCAN_Function.html) | Search argument, string to be searched {, start position} | First position of search argument in string, or zero if not found. |
| [%SECONDS](SECONDS_Function.html) | number | A time or timestamp value with the appropriate number of seconds added or subtracted. |
| [%SQRT](SQRT_Function.html) | numeric expression | The square root of the numeric expression. |
| [%SUBDT](SUBDT_Function.html) | date, time, or timestamp value, { *MSECONDS \| *SECONDS \| *MINUTES \| *HOURS \| *DAYS \| *MONTHS \| *YEARS } | An unsigned numeric value with the extracted portion of a date, time, or timestamp value. |
| [%SUBST](SUBST_Function.html) | String, start {, length} | Substring. |
| [%TIME](TIME_Function.html) | (character, numeric, or timestamp expression {, *ISO \| *HMS \| *USA \| *EUR \| *JIS}) | Value of expression converted to type time or the current system time in ISO format. |
| [%TIMESTAMP](TIMESTAMP_Function.html) | (character, numeric, or timestamp expression {, *ISO \| *ISO0}) | Value of expression converted to type timestamp or the current system timestamp in ISO format. |
| [%TLOOKUP](TLOOKUP_Function.html) | argument, search-table {, alternate_table} | Sets the current table element to the element that satisfies the condition and returns `*ON`, otherwise `*OFF` if no match is found. |
| [%TRIM](TRIM_Function.html) | string | String with left and right blanks trimmed. |
| [%TRIML](TRIML_Function.html) | string | String with left blanks trimmed. |
| [%TRIMR](TRIMR_Function.html) | string | String with right blanks trimmed. |
| [%XFOOT](XFOOT_Function.html) | array expression | Sum of the elements. |
| [%XLATE](XLATE_Function.html) | from, to, string {, start position} | Value translated from String, with any From character values replaced with the corresponding To character values. |
| [%YEARS](YEARS_Function.html) | number | A date or timestamp value with the appropriate number of years added or subtracted. |

### Related Sections
[Encore RPG Language Reference](ecrLrfLangRefMain.html) <br /> Provides a reference of the Encore RPG language. 

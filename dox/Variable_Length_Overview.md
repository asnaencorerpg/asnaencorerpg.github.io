---
title: Variable Length Overview

Id: Variable_Length_Overview
TocParent: aerLrfVariablesMain
TocOrder: 45


---

The Encore RPG compiler can internally define variable-length characters from an externally described file or data structure as fixed-length character fields. 

- Your Encore RPG program can perform any valid character calculation operations on the declared fixed-length field. However, because of the structure of the field, the first two bytes of the field must contain valid unsigned integer data when the field is written to a file. An I/O exception error will occur for an output operation if the first two bytes of the field contain invalid field-length data.
- Control-level indicators, match field entries, and field indicators are not allowed on an input specification if the input field is a variable-length field from an externally described input file.
- Sequential-within-limits processing is not allowed when a file contains variable-length key fields.
- Keyed operations are not allowed when factor 1 of a keyed operation corresponds to a variable-length key field in an externally described file.
- The Encore RPG compiler will place a default value in the output buffer of a newly added record if the variable-length field you chose to output is either not specified on the output specification or it is ignored in the Encore RPG program. The default is zero in the first two bytes and blanks in all of the remaining bytes.
- If you want to change converted variable-length fields, ensure that the current field length is correct. One way to do this is:
<ul>
- Define a data structure with the variable-length field name as a subfield name.
- Define a 5-digit unsigned integer subfield overlaying the beginning of the field, and define an N-byte character subfield overlaying the field starting at position 3.
- Update the field.

</ul>


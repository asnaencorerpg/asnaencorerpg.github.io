---
title: "*Date Data Type"

Id: Date_Data_Type
TocParent: aerLrfDataTypesMain
TocOrder: 4

---


 ***Date**  variables are stored as IEEE 64-bit (8-byte) integers that
        represent dates ranging from January 1 of the year 1 through December 31 of the
        year 9999, and times from 0:00:00 (midnight) through 11:59:59 PM.

  ***Date** 
        constants or variables used in comparisons or assignments do not have to be in
        the same format or use the same separators. Also, dates used for I/O operations
        such as input fields, output fields or key fields are also converted (if
        required) to the necessary format for the operation.

***Date**  fields have a predetermined size and format. The default
        internal format for date variables is ***ISO** .

There are two kinds of date data formats: 2-digit and 4-digit year formats. For
        2-digit year formats, years in the range 1940 to 2039 can be represented. This
        leads to the possibility of a date overflow condition occurring when converting
        from a 4-digit year format to a 2-digit year format.

See the following **topics** for the date data type formats and * **LOVAL** , * **HIVAL** 
        and default values.
        
 + [Date Formats](Date_Formats.html)
 + [Default Values for all DateFormats](Default_Values_for_all_Date_Formats.html)

The equivalent .NET data type is System.DateTime.

### Example
For **examples**  how to code date fields, see the examples in the following topics:
        
 + [Date Operations](Date_Operations.html)
 + [ADDDUR](ADDDUR.html)
 + [MOVE](MOVE.html)
 + [Moving Date and Time](Moving_Data_Time_Data.html)
 + [EXTRACT](EXTRACT.html)
 + [SUBDUR](SUBDUR.html)
 + [TESTTIME](TESTTIME.html)

### See Also
[Data Types](ecrLrfDataTypesMain.html)
[Date and Time](ecrLrfDateandTimeMain.html) 

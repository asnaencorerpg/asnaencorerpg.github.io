---
title: Edit Code Table

Id: sharedEditCodeTable
TocParent: aerLrfEditCodeTable
TocOrder: 10


---

Using the **EditCode** property or keyword allows you to punctuate numeric fields, including $ signs, commas, periods, minus sign, and floating minus according to the standard RPG edit code rules. Enter a valid edit code as listed in the table below that gives you the desired display. For example, using EditCode **J** will display .00, giving you commas, decimals points, and a minus sign when necessary. 




| Edit Code | Commas | Decimal Point | Sign for Negative Balance | Display<br/>(US Regional Settings) | Zero Suppress |
| --------- | :----: | :-----------: | ------------------------- | ---------------------------------- | ------------- |
| 1              | Yes    | Yes           | No Sign                   | .00 or 0  | Yes           |
| 2              | Yes    | Yes           | No Sign                   | Blanks    | Yes           |
| 3              |        | Yes           | No Sign                   | .00 or 0  | Yes           |
| 4              |        | Yes           | No Sign                   | Blanks    | Yes           |
| 5-9<sup>1</sup> |        |               |                           |           |               |
| A              | Yes    | Yes           | CR                        | .00 or 0  | Yes           |
| B              | Yes    | Yes           | CR                        | Blanks    | Yes           |
| C              |        | Yes           | CR                        | .00 or 0  | Yes           |
| D              |        | Yes           | CR                        | Blanks    | Yes           |
| J              | Yes    | Yes           | - (minus)                 | .00 or 0  | Yes           |
| K              | Yes    | Yes           | - (minus)                 | Blanks    | Yes           |
| L              |        | Yes           | - (minus)                 | .00 or 0  | Yes           |
| M              |        | Yes           | - (minus)                 | Blanks    | Yes           |
| N              | Yes    | Yes           | - (floating minus)        | .00 or 0  | Yes           |
| O              | Yes    | Yes           | - (floating minus)        | Blanks    | Yes           |
| P              |        | Yes           | - (floating minus)        | .00 or 0  | Yes           |
| Q              |        | Yes           | - (floating minus)        | Blanks    | Yes           |
| X<sup>2</sup>  |        |               |                           |           |               |
| Y<sup>3</sup>  |        |               |                           |           | Yes           |
| Z<sup>4</sup>  |        |               |                           |           | Yes           |


>Notes:

1. User-defined edit codes.
2. The X edit code ensures a hexadecimal F sign for positive values. Because the system does this for you, normally you do not have to specify this code.
3. The Y edit code suppresses the leftmost zeros of date fields, up to but not including the digit preceding the first separator. The Y edit code also inserts slashes (/) between the month, day, and year according to the following pattern:
<br> 
       The `Y` edit code also inserts slashes (/) between the month, day, and year according to the following pattern:

       nn/n
       nn/nn
       nn/nn/n
       nn/nn/nn
       nnn/nn/nn
       nn/nn/nnnn    (*)
       nnn/nn/nnnn   (*)
       nnnn/nn/nn    (*)
       nnnnn/nn/nn   (*)

4. The Z edit code removes the sign (plus or minus) from a numeric field and suppresses leading zeros.


>(*) : To select between the two different formats for 8 and 9 digit values use the `DatEdit` Project Setting or the `DatEdit` keyword of the `BegClass` command. The default is Y (nnnn/nn/nn).





### See Also

[EditWord Usage](sharedEditWordTable.html)

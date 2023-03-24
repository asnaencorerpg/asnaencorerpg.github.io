---
title: Rules of Subroutine Overloading

Id: aerConRulesofSubroutineOverloading
TocParent: aerConLanguageConceptsMain
TocOrder: 70


---

**When you overload a subroutine, the following rules apply:** 

- Each overloaded version must use the same subroutine name.
- Each overloaded version must differ from all other overloaded versions in at
                least one of the following respects:
                <ul type="disc">
                    <li>
                        Number of arguments.
- Order of the arguments.
- Data types of the arguments.

</li>
        </ul>

The compiler uses the subroutine name and the argument list to check that the call correctly matches the definition. These items are collectively called the *signature* of the subroutine. 

You cannot overload a subroutine without varying the argument list. In particular, you cannot overload a subroutine by varying only one or more of the following items: 

- Access modifier keywords, such as ```*Public```, ```*Shared.```
- Argument names.
- Argument modifier keywords, such as ```*ByRef.```
- The data type of the return value.

The items in the preceding list are not part of the signature.
<blockquote class="dtBlock">
            <b class="le">Note</b> &#8211; If you intend
            to pass a late-bound object variable to an overloaded subroutine, you must
            declare the appropriate argument as ```*Object```.
            <br />
        </blockquote>


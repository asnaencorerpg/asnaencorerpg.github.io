---
title: BEEP

Id: BEEP
TocParent: aerLrfOpCodesMain
TocOrder: 30


---

Sounds a tone through the computer's speaker. 

```
     BEEP
SoundType (Special Value)
Err (Indicator Variable | *Extended)
```

### Parts

**SoundType** 

Optional. Specifies the type of sound to be used by indicating a **special value** that is identified by an entry in the [SOUNDS] section of the registry.


<table class="MsoNormalTable" id="Table2" style="MARGIN-LEFT: 12pt; WIDTH: 97.5%" cellspacing="0" cellpadding="0" width="97%" border="0"> <tr style="mso-yfti-irow: 0; mso-yfti-firstrow: yes"> <td colspan="1" rowspan="1" valign="top" width="144"> <p class="MsoNormal" style="MARGIN: 4pt 0in 4pt 0.1in"> *Std 
</td>
        <td colspan="1" rowspan="1" valign="top" width="438">

Beep using the computer speaker. 
</td>
        </tr>
        <tr style="mso-yfti-irow: 1">
            <td colspan="1" rowspan="1" valign="top" width="144">

*Asterisk 
</td>
            <td colspan="1" rowspan="1" valign="top" width="438">

System asterisk. 
</td>
        </tr>
        <tr style="mso-yfti-irow: 2">
            <td colspan="1" rowspan="1" valign="top" width="144">

*Exclamation 
</td>
            <td colspan="1" rowspan="1" valign="top" width="438">

System exclamation. 
</td>
        </tr>
        <tr style="mso-yfti-irow: 3">
            <td colspan="1" rowspan="1" valign="top" width="144">

*Hand 
</td>
            <td colspan="1" rowspan="1" valign="top" width="438">

System hand. 
</td>
        </tr>
        <tr style="mso-yfti-irow: 4">
            <td colspan="1" rowspan="1" valign="top" width="144">

*Question 
</td>
            <td colspan="1" rowspan="1" valign="top" width="438">

System question. 
</td>
        </tr>
        <tr style="mso-yfti-irow: 5; mso-yfti-lastrow: yes">
            <td colspan="1" rowspan="1" valign="top" width="144">

*SysDft 
</td>
            <td colspan="1" rowspan="1" valign="top" width="438">

System default. 
</td>
        </tr>
</table>
 **Err** 
        

Optional. Will be set if any error condition is found with the file. The following rules apply: 

- **Err** (Indicator Variable) - The specified Indicator is set if an error occurred.
- **Err** (*EXTENDED) - A program status flag is set whose status can be checked using the [%ERROR](ERROR_Function.html) built-in function.
- If the **Err** keyword is not given and an error occurs, a runtime exception will be thrown.

### Example
The frequency and duration of the beep depend on your hardware and system software and may vary among computers. 

After queuing the sound, the **BEEP** op code returns control to the calling function and plays the sound asynchronously. 

If the system cannot play the specified sound, **BEEP** will attempt to play the system default sound. If the system default sound does not play, the function produces a standard beep sound. 

Whether or not your system produces a sound, regardless of the type, depends on the setting in the **Settings - Control Panel - Sounds** application. If it is set to **No Sounds** scheme, then **no** sound will be produced, as shown below. To change, click on the arrow to the right and set to **Windows Default** . 

![](Images/beep.gif) 

### See Also
[Custom Attributes](ecrConCustomAttributes.html)

[ENDCLASS](ENDCLASS.html)

[Understanding Classes](ecrTourUnderstandingClassesMain.html) 

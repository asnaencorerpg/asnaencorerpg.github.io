---
title: Setting Colors

Id: aerLrfSettingColors
TocParent: aerLrfLangElementsMain
TocOrder: 15

---

When setting colors at design-time, click on the right side of the property at the ![](Images/SHG00064_shg.jpg). Three tabs appear, **Custom** , **Web** , and **System** . Not all color names may be recognized by other browsers. So when specifying color values for Web pages to work across different browsers, use the RGB color values. 

### Custom:
When the Custom tab is selected, the following is displayed.

![](Images/customcolors.jpg) 

When a custom color is selected that is not also a "named" color, three separate color intensities compose the color. These three color components are combined into one number, which is what the property is. The code behind generated for a custom color will look something like the following (where *ForeColor* represents the property being set): 

```
 **FromArgb((255 *As System.Byte), (192 *As System.Byte), (255 *As System.Byte))** 
        
```

If the custom color is a "named" color, the code behind generated will look something like: 

```
*this.ForeColor = System.Drawing.Color. **Red** 
```

### Web
When the Web tab is selected, the following is displayed.
![](Images/webcolors.jpg)

Setting colors for a form or control at design-time uses the structure. The code behind generated will look something like the following (where *BackColor* represents the property being set): 

```
*this.BackColor = System.Drawing.Color. **LightGray** 
```

Setting colors for a cell, field, or record in a subfile at run-time also uses the **System.Drawing.Color** structure. The order in which the properties are set, determines the actual color displayed. If you set the color for a cell and then set the color for the field or record in which the cell resides, the last color setting overrides the previous color setting for the cell. The same applies to setting a field which can be overridden by setting the color of the record in which that field resides. 

For example:

```
/* sets the background color of field 2 to yellow
 mySubfile.FieldBackColor[1] = System.Drawing.Color.Yellow 
```
<table class="fineprint" id="Table5" width="50" cellspacing="1" cellpadding="0" border="1">
            <tr>
                <td colspan="1" rowspan="1" width="15">(0,0)Rec1/Fld1</td>
                <td colspan="1" rowspan="1" width="15" bgcolor="yellow">(0,1)Rec1/Fld2</td>
            </tr>
            <tr>
                <td colspan="1" rowspan="1" width="15">(1,0)Rec2/Fld1</td>
                <td colspan="1" rowspan="1" width="15" bgcolor="yellow">(1,1)Rec2/Fld2</td>
            </tr>
</table>
        
```
 /* sets the background color of a cell to red  
 mySubfile.CellBackColor[0,0] = System.Drawing.Color.Red
```
<table class="fineprint" id="Table6" width="50" cellspacing="1" cellpadding="0" border="1">
            <tr>
                <td colspan="1" rowspan="1" width="15" bgcolor="red">(0,0)Rec1/Fld1</td>
                <td colspan="1" rowspan="1" width="15" bgcolor="yellow">(0,1)Rec1/Fld2</td>
            </tr>
            <tr>
                <td colspan="1" rowspan="1" width="15">(1,0)Rec2/Fld1</td>
                <td colspan="1" rowspan="1" width="15" bgcolor="yellow">(1,1)Rec2/Fld2</td>
            </tr>
</table>
        
```
/* set the background color of record 2 to Gold (which overrides field 2/record 2 from yellow to gold)  
 mySubfile.RecordBackColor[1] = System.Drawing.Color.Gold
```

**Finally Results in:** 
<table class="fineprint" id="Table2" width="50" cellspacing="1" cellpadding="0" border="1">
            <tr>
                <td colspan="1" rowspan="1" width="15" bgcolor="red">(0,0)Rec1/Fld1</td>
                <td colspan="1" rowspan="1" width="15" bgcolor="yellow">(0,1)Rec1/Fld2</td>
            </tr>
            <tr>
                <td colspan="1" rowspan="1" width="15" bgcolor="gold">(1,0)Rec2/Fld1</td>
                <td colspan="1" rowspan="1" width="15" bgcolor="gold">(1,1)Rec2/Fld2</td>
            </tr>
</table>
        <br />

However, by changing the order in which the commands are executed, you can also change how the subfile data will appear. 

For example:

```
/* sets the background color of a cell to red  
 mySubfile.CellBackColor[0,0] = System.Drawing.Color.Red
```
<table class="fineprint" id="Table7" width="50" cellspacing="1" cellpadding="0" border="1">
            <tr>
                <td colspan="1" rowspan="1" width="15" bgcolor="red">(0,0)Rec1/Fld1</td>
                <td colspan="1" rowspan="1" width="15">(0,1)Rec1/Fld2</td>
            </tr>
            <tr>
                <td colspan="1" rowspan="1" width="15">(1,0)Rec2/Fld1</td>
                <td colspan="1" rowspan="1" width="15">(1,1)Rec2/Fld2</td>
            </tr>
</table>
        <pre class="prettyprint"> /* set the background color of record 2 to Gold  
 mySubfile.RecordBackColor[1] = System.Drawing.Color.Gold</pre>
<table class="fineprint" id="Table8" width="50" cellspacing="1" cellpadding="0" border="1">
            <tr>
                <td colspan="1" rowspan="1" width="15" bgcolor="red">(0,0)Rec1/Fld1</td>
                <td colspan="1" rowspan="1" width="15">(0,1)Rec1/Fld2</td>
            </tr>
            <tr>
                <td colspan="1" rowspan="1" width="15" bgcolor="gold">(1,0)Rec2/Fld1</td>
                <td colspan="1" rowspan="1" width="15" bgcolor="gold">(1,1)Rec2/Fld2</td>
            </tr>
</table>
        
```
/* sets the background color of field 2 to yellow (which changes field 2/record 2 from gold to yellow).
 mySubfile.FieldBackColor[1] = System.Drawing.Color.Yellow 
```

**Finally Results in:** 
<table class="fineprint" id="Table4" width="50" cellspacing="1" cellpadding="0" border="1">
            <tr>
                <td colspan="1" rowspan="1" width="15" bgcolor="red">(0,0)Rec1/Fld1</td>
                <td colspan="1" rowspan="1" width="15" bgcolor="yellow">(0,1)Rec1/Fld2</td>
            </tr>
            <tr>
                <td colspan="1" rowspan="1" width="15" bgcolor="gold">(1,0)Rec2/Fld1</td>
                <td colspan="1" rowspan="1" width="15" bgcolor="yellow">(1,1)Rec2/Fld2</td>
            </tr>
</table>
        <br />

The following table shows the **System.Drawing.Color. *<u>color</u>* ** , the hexadecimal number equivalent, and the red, green, and blue decimal values. The hexadecimal values are preceded by the pound character (#), in the form **#RRGGBB** . **RR** , **GG** , and **BB** represent hexadecimal values from 0 to 255 that indicate the red, green, and blue components of a color, respectively. 
<table class="fineprint" id="Table3" cellspacing="1" cellpadding="0" bgcolor="black" border="3">
                <tr>
                    <td align="center" colspan="1" rowspan="1" width="130" bgcolor="aliceblue">
                        aliceblue<br />
                        (#F0F8FF)<br />
                        240,248,255
                    </td>
                    <td align="center" colspan="1" rowspan="1" width="130" bgcolor="antiquewhite">
                        antiquewhite<br />
                        (#FAEBD7)<br />
                        250,235,215
                    </td>
                    <td align="center" colspan="1" rowspan="1" width="130" bgcolor="aqua">
                        aqua<br />
                        (#00FFFF)<br />
                        0,255,255
                    </td>
                    <td align="center" colspan="1" rowspan="1" width="130" bgcolor="aquamarine">
                        aquamarine<br />
                        (#7FFFD4)<br />
                        127,255,212
                    </td>
                    <td align="center" colspan="1" rowspan="1" width="130" bgcolor="azure">
                        azure<br />
                        (#F0FFFF)<br />
                        240,255,255
                    </td>
                </tr>
                <tr>
                    <td align="center" colspan="1" rowspan="1" bgcolor="beige">
                        beige<br />
                        (#F5F5DC)<br />
                        245,245,220
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="bisque">
                        bisque<br />
                        (#FFE4C4)<br />
                        255,228,196
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="black">
 black<br />
                            (#000000)<br />
                            0,0,0
 </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="blanchedalmond">
                        blanchedalmond<br />
                        (#FFEBCD)<br />
                        255,235,205
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="#0000ff">
 blue<br />
                            (#0000FF)<br />
                            0,0,255
 </td>
                </tr>
                <tr>
                    <td align="center" colspan="1" rowspan="1" bgcolor="#8a2be2">
                        blueviolet<br />
                        (#8A2BE2)<br />
                        138,43,226
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="brown">
                        brown<br />
                        (#A52A2A)<br />
                        165,42,42
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="burlywood">
                        burlywood<br />
                        (#DEB887)<br />
                        222,184,135
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="cadetblue">
                        cadetblue<br />
                        (#5F9EA0)<br />
                        95,158,160
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="chartreuse">
                        chartreuse<br />
                        (#7FFF00)<br />
                        127,255,0
                    </td>
                </tr>
                <tr>
                    <td align="center" colspan="1" rowspan="1" bgcolor="chocolate">
                        chocolate<br />
                        (#D2691E)<br />
                        210,105,30
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="coral">
                        coral<br />
                        (#FF7F50)<br />
                        255,127,80
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="#6495ed">
                        cornflowerblue<br />
                        (#6495ED)<br />
                        100,149,237
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="cornsilk">
                        cornsilk<br />
                        (#FFF8DC)<br />
                        255,248,220
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="crimson">
                        crimson<br />
                        (#DC143C)<br />
                        220,20,60
                    </td>
                </tr>
                <tr>
                    <td align="center" colspan="1" rowspan="1" bgcolor="cyan">
                        cyan<br />
                        (#00FFFF)<br />
                        0,255,255
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="darkblue">
 darkblue<br />
                            (#00008B)<br />
                            0,0,139
 </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="darkcyan">
                        darkcyan<br />
                        (#008B8B)<br />
                        0,139,139
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="darkgoldenrod">
                        darkgoldenrod<br />
                        (#B8860B)<br />
                        184,134,11
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="darkgray">
                        darkgray<br />
                        (#A9A9A9)<br />
                        169,169,169
                    </td>
                </tr>
                <tr>
                    <td align="center" colspan="1" rowspan="1" bgcolor="darkgreen">
                        darkgreen<br />
                        (#006400)<br />
                        0,100,0
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="darkkhaki">
                        darkkhaki<br />
                        (#BDB76B)<br />
                        189,183,107
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="darkmagenta">
                        darkmagenta<br />
                        (#8B008B)<br />
                        139,0,139
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="darkolivegreen">
                        darkolivegreen<br />
                        (#556B2F)<br />
                        85,107,47
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="darkorange">
                        darkorange<br />
                        (#FF8C00)<br />
                        255,140,0
                    </td>
                </tr>
                <tr>
                    <td align="center" colspan="1" rowspan="1" bgcolor="darkorchid">
                        darkorchid<br />
                        (#9932CC)<br />
                        153,50,204
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="darkred">
                        darkred<br />
                        (#8B0000)<br />
                        139,0,0
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="darksalmon">
                        darksalmon<br />
                        (#E9967A)<br />
                        233,150,122
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="darkseagreen">
                        darkseagreen<br />
                        (#8FBC8B)<br />
                        143,188,143
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="darkslateblue">
 darkslateblue<br />
                            (#483D8B)<br />
                            72,61,139
 </td>
                </tr>
                <tr>
                    <td align="center" colspan="1" rowspan="1" bgcolor="darkslategray">
 darkslategray<br />
                            (#2F4F4F)<br />
                            47,79,79
 </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="darkturquoise">
                        darkturquoise<br />
                        (#00CED1)<br />
                        0,206,209
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="darkviolet">
                        darkviolet<br />
                        (#9400D3)<br />
                        148,0,211
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="deeppink">
                        deeppink<br />
                        (#FF1493)<br />
                        255,20,147
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="deepskyblue">
                        deepskyblue<br />
                        (#00BFFF)<br />
                        0,191,255
                    </td>
                </tr>
                <tr>
                    <td align="center" colspan="1" rowspan="1" bgcolor="dimgray">
                        dimgray<br />
                        (#696969)<br />
                        105,105,105
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="dodgerblue">
                        dodgerblue<br />
                        (#1E90FF)<br />
                        30,144,255
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="firebrick">
                        firebrick<br />
                        (#B22222)<br />
                        178,34,34
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="floralwhite">
                        floralwhite<br />
                        (#FFFAF0)<br />
                        255,250,240
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="forestgreen">
                        forestgreen<br />
                        (#228B22)<br />
                        34,139,34
                    </td>
                </tr>
                <tr>
                    <td align="center" colspan="1" rowspan="1" bgcolor="#ff00ff">
                        fuchsia<br />
                        (#FF00FF)<br />
                        255,0,255
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="gainsboro">
                        gainsboro<br />
                        (#DCDCDC)<br />
                        220,220,220
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="ghostwhite">
                        ghostwhite<br />
                        (#F8F8FF)<br />
                        248,248,255
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="gold">
                        gold<br />
                        (#FFD700)<br />
                        255,215,0
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="goldenrod">
                        goldenrod<br />
                        (#DAA520)<br />
                        218,165,32
                    </td>
                </tr>
                <tr>
                    <td align="center" colspan="1" rowspan="1" bgcolor="gray">
                        gray<br />
                        (#808080)<br />
                        128,128,128
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="green">
                        green<br />
                        (#008000)<br />
                        0,128,0
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="greenyellow">
                        greenyellow<br />
                        (#ADFF2F)<br />
                        173,255,47
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="honeydew">
                        honeydew<br />
                        (#F0FFF0)<br />
                        240,255,240
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="hotpink">
                        hotpink<br />
                        (#FF69B4)<br />
                        255,105,180
                    </td>
                </tr>
                <tr>
                    <td align="center" colspan="1" rowspan="1" bgcolor="indianred">
                        indianred<br />
                        (#CD5C5C)<br />
                        205,92,92
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="indigo">
 indigo<br />
                            (#4B0082)<br />
                            75,0,130
 </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="ivory">
                        ivory<br />
                        (#FFFFF0)<br />
                        255,255,240
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="khaki">
                        khaki<br />
                        (#F0E68C)<br />
                        240,230,140
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="lavender">
                        lavender<br />
                        (#E6E6FA)<br />
                        230,230,250
                    </td>
                </tr>
                <tr>
                    <td align="center" colspan="1" rowspan="1" bgcolor="lavenderblush">
                        lavenderblush<br />
                        (#FFF0F5)<br />
                        255,240,245
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="lawngreen">
                        lawngreen<br />
                        (#7CFC00)<br />
                        124,252,0
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="lemonchiffon">
                        lemonchiffon<br />
                        (#FFFACD)<br />
                        255,250,205
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="lightblue">
                        lightblue<br />
                        (#ADD8E6)<br />
                        173,216,230
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="lightcoral">
                        lightcoral<br />
                        (#F08080)<br />
                        240,128,128
                    </td>
                </tr>
                <tr>
                    <td align="center" colspan="1" rowspan="1" bgcolor="lightcyan">
                        lightcyan<br />
                        (#E0FFFF)<br />
                        224,255,255
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="lightgoldenrodyellow">
                        lightgoldenrodyellow<br />
                        (#FAFAD2)<br />
                        250,250,210
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="lightgreen">
                        lightgreen<br />
                        (#90EE90)<br />
                        144,238,144
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="lightgrey">
                        lightgrey<br />
                        (#D3D3D3)<br />
                        211,211,211
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="lightpink">
                        lightpink<br />
                        (#FFB6C1)<br />
                        255,182,193
                    </td>
                </tr>
                <tr>
                    <td align="center" colspan="1" rowspan="1" bgcolor="lightsalmon">
                        lightsalmon<br />
                        (#FFA07A)<br />
                        255,160,122
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="lightseagreen">
                        lightseagreen<br />
                        (#20B2AA)<br />
                        32,178,170
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="lightskyblue">
                        lightskyblue<br />
                        (#87CEFA)<br />
                        135,206,250
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="lightslategray">
                        lightslategray<br />
                        (#778899)<br />
                        119,136,153
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="lightsteelblue">
                        lightsteelblue<br />
                        (#B0C4DE)<br />
                        176,196,222
                    </td>
                </tr>
                <tr>
                    <td align="center" colspan="1" rowspan="1" bgcolor="lightyellow">
                        lightyellow<br />
                        (#FFFFE0)<br />
                        255,255,224
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="lime">
                        lime<br />
                        (#00FF00)<br />
                        0,255,0
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="limegreen">
                        limegreen<br />
                        (#32CD32)<br />
                        50,205,50
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="linen">
                        linen<br />
                        (#FAF0E6)<br />
                        250,240,230
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="magenta">
                        magenta<br />
                        (#FF00FF)<br />
                        255,0,255
                    </td>
                </tr>
                <tr>
                    <td align="center" colspan="1" rowspan="1" bgcolor="maroon">
                        maroon<br />
                        (#800000)<br />
                        128,0,0
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="mediumaquamarine">
                        mediumaquamarine<br />
                        (#66CDAA)<br />
                        102,205,170
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="mediumblue">
 mediumblue<br />
                            (#0000CD)<br />
                            0,0,205
 </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="mediumorchid">
                        mediumorchid<br />
                        (#BA55D3)<br />
                        186,85,211
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="mediumpurple">
                        mediumpurple<br />
                        (#9370DB)<br />
                        147,112,219
                    </td>
                </tr>
                <tr>
                    <td align="center" colspan="1" rowspan="1" bgcolor="mediumseagreen">
                        mediumseagreen<br />
                        (#3CB371)<br />
                        60,179,113
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="mediumslateblue">
                        mediumslateblue<br />
                        (#7B68EE)<br />
                        123,104,238
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="mediumspringgreen">
                        mediumspringgreen<br />
                        (#00FA9A)<br />
                        0,250,154
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="mediumturquoise">
                        mediumturquoise<br />
                        (#48D1CC)<br />
                        72,209,204
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="mediumvioletred">
                        mediumvioletred<br />
                        (#C71585)<br />
                        199,21,133
                    </td>
                </tr>
                <tr>
                    <td align="center" colspan="1" rowspan="1" bgcolor="midnightblue">
 midnightblue<br />
                            (#191970)<br />
                            25,25,112
 </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="mintcream">
                        mintcream<br />
                        (#F5FFFA)<br />
                        245,255,250
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="mistyrose">
                        mistyrose<br />
                        (#FFE4E1)<br />
                        255,228,225
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="moccasin">
                        moccasin<br />
                        (#FFE4B5)<br />
                        255,228,181
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="navajowhite">
                        navajowhite<br />
                        (#FFDEAD)<br />
                        255,222,173
                    </td>
                </tr>
                <tr>
                    <td align="center" colspan="1" rowspan="1" bgcolor="navy">
 navy<br />
                            (#000080)<br />
                            0,0,128
 </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="oldlace">
                        oldlace<br />
                        (#FDF5E6)<br />
                        253,245,230
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="olive">
                        olive<br />
                        (#808000)<br />
                        128,128,0
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="olivedrab">
                        olivedrab<br />
                        (#6B8E23)<br />
                        107,142,35
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="orange">
                        orange<br />
                        (#FFA500)<br />
                        255,165,0
                    </td>
                </tr>
                <tr>
                    <td align="center" colspan="1" rowspan="1" bgcolor="orangered">
                        orangered<br />
                        (#FF4500)<br />
                        255,69,0
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="orchid">
                        orchid<br />
                        (#DA70D6)<br />
                        218,112,214
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="palegoldenrod">
                        palegoldenrod<br />
                        (#EEE8AA)<br />
                        238,232,170
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="palegreen">
                        palegreen<br />
                        (#98FB98)<br />
                        152,251,152
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="paleturquoise">
                        paleturquoise<br />
                        (#AFEEEE)<br />
                        175,238,238
                    </td>
                </tr>
                <tr>
                    <td align="center" colspan="1" rowspan="1" bgcolor="palevioletred">
                        palevioletred<br />
                        (#DB7093)<br />
                        219,112,147
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="papayawhip">
                        papayawhip<br />
                        (#FFEFD5)<br />
                        255,239,213
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="peachpuff">
                        peachpuff<br />
                        (#FFDAB9)<br />
                        255,218,185
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="peru">
                        peru<br />
                        (#CD853F)<br />
                        205,133,63
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="pink">
                        pink<br />
                        (#FFC0CB)<br />
                        255,192,203
                    </td>
                </tr>
                <tr>
                    <td align="center" colspan="1" rowspan="1" bgcolor="plum">
                        plum<br />
                        (#DDA0DD)<br />
                        221,160,221
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="powderblue">
                        powderblue<br />
                        (#B0E0E6)<br />
                        176,224,230
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="purple">
                        purple<br />
                        (#800080)<br />
                        128,0,128
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="red">
                        red<br />
                        (#FF0000)<br />
                        255,0,0
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="rosybrown">
                        rosybrown<br />
                        (#BC8F8F)<br />
                        188,143,143
                    </td>
                </tr>
                <tr>
                    <td align="center" colspan="1" rowspan="1" bgcolor="royalblue">
                        royalblue<br />
                        (#4169E1)<br />
                        65,105,225
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="saddlebrown">
                        saddlebrown<br />
                        (#8B4513)<br />
                        139,69,19
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="salmon">
                        salmon<br />
                        (#FA8072)<br />
                        250,128,114
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="sandybrown">
                        sandybrown<br />
                        (#F4A460)<br />
                        244,164,96
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="seagreen">
                        seagreen<br />
                        (#2E8B57)<br />
                        46,139,87
                    </td>
                </tr>
                <tr>
                    <td align="center" colspan="1" rowspan="1" bgcolor="seashell">
                        seashell<br />
                        (#FFF5EE)<br />
                        255,245,238
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="sienna">
                        sienna<br />
                        (#A0522D)<br />
                        160,82,45
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="silver">
                        silver<br />
                        (#C0C0C0)<br />
                        192,192,192
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="skyblue">
                        skyblue<br />
                        (#87CEEB)<br />
                        135,206,235
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="slateblue">
                        slateblue<br />
                        (#6A5ACD)<br />
                        106,90,205
                    </td>
                </tr>
                <tr>
                    <td align="center" colspan="1" rowspan="1" bgcolor="slategray">
                        slategray<br />
                        (#708090)<br />
                        112,128,144
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="snow">
                        snow<br />
                        (#FFFAFA)<br />
                        255,250,250
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="springgreen">
                        springgreen<br />
                        (#00FF7F)<br />
                        0,255,127
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="steelblue">
                        steelblue<br />
                        (#4682B4)<br />
                        70,130,180
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="tan">
                        tan<br />
                        (#D2B48C)<br />
                        210,180,140
                    </td>
                </tr>
                <tr>
                    <td align="center" colspan="1" rowspan="1" bgcolor="teal">
                        teal<br />
                        (#008080)<br />
                        0,128,128
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="thistle">
                        thistle<br />
                        (#D8BFD8)<br />
                        216,191,216
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="tomato">
                        tomato<br />
                        (#FF6347)<br />
                        255,99,71
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="turquoise">
                        turquoise<br />
                        (#40E0D0)<br />
                        64,224,208
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="violet">
                        violet<br />
                        (#EE82EE)<br />
                        238,130,238
                    </td>
                </tr>
                <tr>
                    <td align="center" colspan="1" rowspan="1" bgcolor="wheat">
                        wheat<br />
                        (#F5DEB3)<br />
                        245,222,179
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="white">
                        white<br />
                        (#FFFFFF)<br />
                        255,255,255
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="whitesmoke">
                        whitesmoke<br />
                        (#F5F5F5)<br />
                        245,245,245
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="yellow">
                        yellow<br />
                        (#FFFF00)<br />
                        255,255,0
                    </td>
                    <td align="center" colspan="1" rowspan="1" bgcolor="yellowgreen">
                        yellowgreen<br />
                        (#9ACD32)<br />
                        154,205,50
                    </td>
                </tr>
</table>

### System
The system colors are used to paint various parts of the display. Selecting a system color creates a **SystemColors** color structure that is the color of a windows display element. See for a complete list of the members. When the System tab is selected, the following is displayed: 

![](Images/systemcolors.jpg) 

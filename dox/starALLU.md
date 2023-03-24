---
title: "*ALLU"

Id: starALLU
TocParent: aerLrfFigConstantsMain
TocOrder: 1


---

The ***ALLU** is a figurative constant of the form *ALLU’XxxxYyyy’. It indicates a literal of the form ’XxxxYyyyXxxxYyyy...’, and has a length determined by the length of the field that is associated with the *ALLU’XxxxYyyy’ constant. 

Each double-byte character in the constant is represented by four hexadecimal digits. For example, *ALLU’0041’ represents a string of repeated UCS-2 ’A’s. 

**Example:** 

```
Using System

BegClass starall Access(*Public)
	dclfld		Chara		*char	Len(10) inz( ***allU** "004100420043")
	dclfld		CharB		*char	Len(10) inz( *all"ABC")

	BegConstructor Access(*Public)

		console.WriteLine( CharA + " = ABCABCABCA  CharA")
		console.WriteLine( CharB + " = ABCABCABCA  CharB")

		compare charA  *allU"004100420043"  eq(*in03)	
		compare charB  *all"ABC"			eq(*in04)	

		If *in03
			console.WriteLine( Chara + " compare = ABCABCABCA CharA")
		else
			console.WriteLine( Chara + " compare &lt;&gt; ABCABCABCA CharA")
		endif

		If *in04
			console.WriteLine( CharB + " compare = ABCABCABCA CharB")
		else
			console.WriteLine( CharB + " compare &lt;&gt; ABCABCABCA CharB")
		endif

		If CharA = *allU"004100420043"
			console.WriteLine( Chara + " If = ABCABCABCA CharA")
		else
			console.WriteLine( Chara + " If &lt;&gt; ABCABCABCA CharA")
		endif

		If CharB = *ALL"ABC"
			console.WriteLine( CharB + " If = ABCABCABCA CharB")
		else
			console.WriteLine( CharB + " If &lt;&gt; ABCABCABCA CharB")
		endif	

		move *allU"0030003100320034" CharA
		move *all"1234" CharB

		console.WriteLine( CharA + " = 1234123412 CharA")
		console.WriteLine( CharB + " = 1234123412 CharB")

		movel *allU"0080" CharA
		movel *all"€" CharB

		console.WriteLine( CharA + " = €€€€€€€€€€ CharA")
		console.WriteLine( CharB + " = €€€€€€€€€€ CharB")

	EndConstructor
	begsr Main Access( *Public )  Shared( *Yes )
		dclSRParm  Args  *string  Rank( 1 )
		*new starAll()
		Console.WriteLine ( "Press &lt;enter&gt; to exit." )
		Console.ReadLine()
	EndSR	
EndClass
```

### See Also
[Figurative Constants](aerLrfFigConstantsMain.html)
[Figurative Constants Rules](Fig_Constants_Rules.html)
[Data Types](aerLrfDataTypesMain.html) 

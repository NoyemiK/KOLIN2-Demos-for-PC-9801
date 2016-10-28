##KOLIN2 Preprocessor Directives

`#mode-86` specifies that the file is meant to be used on PC-9801-86 hardware (OPNA, .mo8 extension)
`#mode-26` specifies that the file is meant to be used on PC-9801-26K hardware (OPN, .mo2 extension)

*Note: Mode 26 files will play on PC-9801-86 and more, but not the other way round, as the PC-9801-26K and Speak Board and other hardware lacks the required components to play 86 music.*

`#octave-rev` reverses the direction of the octave incrementation operator notation.
`#volume-rev` reverses the direction of the volume incrementation operator notation.
`#detune-rev` reverses the direction of the detune incrementation operator notation.

`#include "Filename"` sets additional source files to include.

`#title "Title"` sets the Title metadata for the compiled music.
`#composer "Noyemi"` sets the Composer metadata for the compiled music.
`copyright "(c) 1979 Sunrise"` sets the Copyright metadata for the compiled music.

`#pcmfile "Filename.po8"` sets the PCM block file to be used with the compiled music and triggers PCM from that table.

##KOLIN2 Basic Channel Elements

*The available channels for the user will depend on the mode the source file is written in!*

*FM Channels*:
* ABC (mode 26 or 86)
* DEF (mode 86 only)

*SSG Channels*:
* GHI (mode 26 or 86)

*Rhythm/PCM (mode 86 only)*:
* R (RSS ROM)
* S (PCM)
---

As with PMD and other FM program APIs for some Japanese PCs, you program FM instrument patches by specifying an instrument offset and writing a parameter array for each operator:
~~~
@[1～255] = {	 
    AR, DR, SR, RR, SL, TL, KS, ML, DT,	;Operator 1
		 AR, DR, SR, RR, SL, TL, KS, ML, DT,	;Operator 2
		 AR, DR, SR, RR, SL, TL, KS, ML, DT,	;Operator 3
		 AR, DR, SR, RR, SL, TL, KS, ML, DT,	;Operator 4
    ALG, FB }
~~~
These have the same limitations/values as PMD, with the exception of there being no AMS mask flag.
---

##KOLIN2 Song Sequence Commands

*Comments*: `;, /*`
Any characters on the line after the comment command are ignored.

*Delimiter:* `|`
A useful separator that is not read by the compiler, used to mark parts in a sequence for the programmer's benefit.

*End Mark:* `!`
A command that halts the playback on the channel when it is reached.

*Loop Macro:* `L`
Channel sequence information following this macro is looped infinitely.

*Iterated Loop Macro/Escape:* `[ ... / .. ]n`
Information inside of `[ .. ]` will be looped n times, and optionally escaped on the last iteration by / to cut the loop short.
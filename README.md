# KOLIN2 Demonstrations for PC 9801

[KOLIN2 is an FM sound driver for PC-9801 by Akikaz](http://www.ac.auone-net.jp/~valsound/kolin.html) and found on the VAL-SOUND site. It's also an API for creating FM sound sequence programs for 86 and 26 soundboards (YM2608/OPNA and YM2203/OPN, respectively.)

Included in this repository are .MOx and .MML files; the former will play directly on PC-9801 and emulators, provided the KOLIN2 driver is on your system and initialized before play. To initialize KOLIN2 in DOS, navigate to the directory containing KOLIN2.COM and type `KOLIN2` to load the driver.

##Using KOLIN2

To compile an MML source file to a playable driver instruction file for KOLIN2, type `klc [option] [directory of MML file]`. To play a KOLIN2 driver instruction file, type in `klp [directory of compiled file]`. Make sure to include the extension, as KOLIN2 compiles .MO8 and .MO2 files, depending on the driver mode specified in your source file.

Included in this repository as examples are AMIx.MML files, which are 26 and 86 arrangements of music from [Amihailu in Dreamland](https://noyemi-k.itch.io/amihailu-in-dreamland), used to demonstrate the power of the KOLIN2 driver.

##Examples

[AMI2.MO2](https://soundcloud.com/mishkahd/ami2mo2)
[Pursuit (High)](http://delmunsoft.tumblr.com/post/145409788028/pc-9801-26k-version-of-pursuit-high-from-the)

##Documentation

The first thing you will notice when playing with KOLIN2 is some similarities with NRTDRV and PMD, though it has a few of its very own features.

**Differences From PMD** include:

* Ability to escape loops early in a sequence with the / character. Ex: `[e8r8e8r8 r2 /r1]3` will escape the loop on the 3rd iteration before the whole rest (r1)
* A different tempo system, 0-255. It does not seem to specify BPM but some sort of clock multiplier instead
* All channels available in the current driver mode (86 or 26) must be declared and given instructions. The compiler will complain about unused channels
* KOLIN2 includes its own PCM object linker that compiles a .PO8 file for use with 86 mode
* FM patch sizes do not include an AMS Mask flag like with PMD—patches used with PMD compositions must have this parameter removed before a file will compile
* Board mode must be specified in the MML. If 86 is chosen, the song may not play on 26 hardware at all even if only the YM2203 channels are used

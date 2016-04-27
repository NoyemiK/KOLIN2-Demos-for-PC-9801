# KOLIN2 Demonstrations for PC 9801

[KOLIN2 is an FM sound driver for PC-9801 by Akikaz](http://www.ac.auone-net.jp/~valsound/kolin.html) and found on the VAL-SOUND site. It's also an API for creating FM sound sequence programs for 86 and 26 soundboards (YM2608/OPNA and YM2203/OPN, respectively.)

Included in this repository are .MOx and .MML files; the former will play directly on PC-9801 and emulators, provided the KOLIN2 driver is on your system and initialized before play. To initialize KOLIN2 in DOS, navigate to the directory containing KOLIN2.COM and type `KOLIN2` to load the driver.

##Using KOLIN2

To compile an MML source file to a playable driver instruction file for KOLIN2, type `klc [option] [directory of MML file]`. To play a KOLIN2 driver instruction file, type in `klp [directory of compiled file]`. Make sure to include the extension, as KOLIN2 compiles .MO8 and .MO2 files, depending on the driver mode specified in your source file.

Included in this repository as examples are AMIx.MML files, which are 26 and 86 arrangements of music from [Amihailu in Dreamland](https://noyemi-k.itch.io/amihailu-in-dreamland), used to demonstrate the power of the KOLIN2 driver.

##Examples

[AMI2.MO2](https://soundcloud.com/mishkahd/ami2mo2)
(More to come)

##Documentation

(WIP)

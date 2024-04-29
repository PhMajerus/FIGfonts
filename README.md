# FIGfonts

## Introduction

This repository contains the fonts I created for the [FIGlet utility](http://www.figlet.org/).
While most FIGfonts are ASCII-art, I decided to experiment with ANSI/VT coloring, extended Unicode characters as sub-characters, ...


## Fonts in this repository

### phm-smallvt
![phm-smallvt](images/phm-smallvt.png)
This is my main ANSI/VT-based font, containing over 500 characters.
This font uses extended ASCII characters from the US (437) codepage, and requires an ANSI/VT terminal that supports the underline escape sequence.
It works in FIGlet 2.2.5, but the width computation gets confused, so it requires -w 999 to avoid misplaced line breaks.
It does not work at all in TOIlet 0.3, as escape sequences get removed.
_Remember to use `figlet -w 999` to avoid misplaced line breaks and broken VT control sequences due to bad width computation._

### hp2640-largetype
![hp2640-largetype](images/hp2640-largetype.png)
This is a FIGlet version of the example Large Type Pieces (Unicode 16.0) ASCII font provided by Hewlett-Packard in their HP 2641A/2645A/2645S Display Station Reference Manual, Table B-16.
It is a reference font for large type pieces introduced in Unicode 16.0 but only contains the 96 base characters.
It uses three rows and its look depends on the font design, as large type pieces can be different in different fonts.

### phm-largetype
![phm-largetype](images/phm-largetype.png)
This is my main Large Type Pieces (Unicode 16.0) font, containing over 1000 characters covering Latin-1, Latin Extended-A, Vietnamese and some Latin Extended-B and Extended Additional, superscripts, subscripts, small capitals, number forms, Greek, Cyrillic, Japanese half-width katakana, some mathematical operators and symbols, and more.
It uses Unicode 16 Large Type Pieces (U+1CE1A to U+1CE50) and Quadrants (including the centered variants) to build a smooth set of characters using three rows.
It also uses Sextants and Octants for some non-alphabetical characters such as outlined letters and 7-segment digits.
It requires the terminal to support those characters to display properly, a font such as [Cascadia ≥2404.23](https://github.com/microsoft/cascadia-code) or [Iosevka ≥29.0.0](https://github.com/be5invis/Iosevka) is recommended.
_Remember to use `figlet -C utf8` to access Unicode characters._

### phm-blocky
![phm-blocky](images/phm-blocky.png)
This font uses extended ASCII characters from the US (437) codepage and ANSI/VT escape sequences for inverted (negative) characters.
It uses just two rows and supports the base characters set.
It works in FIGlet 2.2.5, but the width computation gets confused, so it can only be used for single lines. It requires `-w 999` to avoid misplaced line breaks.
It does not work at all in TOIlet 0.3, as escape sequences get removed.
_Remember to use `figlet -w 999` to avoid misplaced line breaks and broken VT control sequences due to bad width computation._

### phm-blocky-reverse
![phm-blocky-reverse](images/phm-blocky-reverse.png)
This font uses extended ASCII characters from the US (437) codepage.
It uses four rows and supports the base characters set.
Unlike phm-blocky, this reverse version does not require an ANSI/VT terminal (does not use escape sequences) and works fine with FIGlet, but the terminal must support the block elements found in codepage 473.
The equivalent font in non-reverse is not possible without help from ANSI/VT to invert (negative) some characters.

### phm-rounded
![phm-rounded](images/phm-rounded.png)
This font uses Unicode characters (Box Drawings lines, half lines, diagonals and arcs).
It uses four rows and supports the base characters set.


## Using & installing FIGfonts
You'll need the FIGlet utility, so start with `sudo apt install figlet` or equivalent for your distro.
FIGfonts can be used as it by specifying their paths:
```
echo 'Hello, world!' | figlet -f /some_path/phm-largetype.flf -C utf8
```
The `-C utf8` option makes it support Unicode characters, handling the input as UTF-8.

But to make it cleaner and easier to use regularly, the font files can be copied to the FIGfont folder:
```
# Find out which directory contains figfonts
figlet -I2
# Copy font file(s) to that directory
sudo cp phm-largetype.flf /usr/share/figlet/phm-largetype.flf
# Use the FIGfont without having to specify the path or extension
echo 'Hello, world!' | figlet -f phm-largetype -C utf8
```


-- Philippe Majerus, April 2024

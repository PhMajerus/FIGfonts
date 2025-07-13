# Philippe Majerus’s FIGfonts collection

![Philippe Majerus’s FIGfonts collection](images/title.png)


## Introduction

This repository contains the fonts I created for the [FIGlet utility](http://www.figlet.org/).
While most FIGfonts are ASCII-art, I decided to experiment with ANSI/VT coloring and extended Unicode characters as sub-characters.


## Fonts in this repository


### phm-smallvt
![phm-smallvt](images/phm-smallvt.png)

This is my main ANSI/VT-based font, containing over 500 characters.
This font uses extended ASCII characters from the US (437) codepage, and requires an ANSI/VT terminal that supports the underline escape sequence.

It works in FIGlet 2.2.5, but the width computation gets confused, so it requires `-w 9999` to avoid misplaced line breaks.
It does not work at all in TOIlet 0.3, as escape sequences get removed.

_Remember to use `figlet -f phm-smallvt -C utf8 -w 9999` to access Unicode characters and to avoid misplaced line breaks and broken VT control sequences due to bad width computation._


### hp2640-largetype
![hp2640-largetype](images/hp2640-largetype.png)

This is a FIGlet version of the example Large Type Pieces (Unicode 16.0) ASCII font provided by Hewlett-Packard in their HP 2641A/2645A/2645S Display Station Reference Manual, Table B-16.
It is a reference font for large type pieces introduced in Unicode 16.0 but only contains the 96 base ASCII characters. It is mostly intended as a historical reference for my own Large Type font below.

It uses Unicode 16 Large Type Pieces (`U+1CE1A` to `U+1CE50`) and Quadrants to build a smooth set of characters using three rows. Its look depends on the font design, as large type pieces can be different in different fonts.

If you want to learn more about Large Type Pieces, try `curl https://raw.githubusercontent.com/PhMajerus/Documents/main/HowTos/HowTo%20Large%20Type%20Pieces.txt`.

This FIGfont requires the terminal to support Large Type Pieces characters to display properly, a font such as [Cascadia ≥2404.23](https://github.com/microsoft/cascadia-code), [Cozette ≥1.27.0](https://github.com/slavfox/Cozette), or [Iosevka ≥29.0.0](https://github.com/be5invis/Iosevka) is recommended.


### phm-largetype
![phm-largetype](images/phm-largetype.png)

This is my main Large Type Pieces (Unicode 16.0) font, containing 1875 characters covering ASCII, Latin-1, Latin Extended-A, Latin Extended-B, Latin Extended Additional, superscripts, subscripts, small capitals, number forms, Greek, Cyrillic, Japanese half-width Katakana, Braille, some mathematical operators and symbols, and more.

It uses Unicode 16 Large Type Pieces (`U+1CE1A` to `U+1CE50`) and Quadrants (including the centered variants) to build a smooth set of characters using three rows.
It also uses Sextants and Octants for some non-alphabetical characters such as outlined letters and 7-segment digits.
Note that because of the limited size, capital letters (uppercase) do not have accents, and small letter (lowercase) are missing some accents, such as marks appearing below characters.

If you want to learn more about Large Type Pieces, try `curl https://raw.githubusercontent.com/PhMajerus/Documents/main/HowTos/HowTo%20Large%20Type%20Pieces.txt`.

This FIGfont requires the terminal to support Large Type Pieces characters to display properly, a font such as [Cascadia ≥2404.23](https://github.com/microsoft/cascadia-code), [Cozette ≥1.27.0](https://github.com/slavfox/Cozette), or [Iosevka ≥29.0.0](https://github.com/be5invis/Iosevka) is recommended.

_Remember to use `figlet -f phm-largetype -C utf8` to access Unicode characters._


### phm-largetype-ASCII
![phm-largetype-ASCII](images/phm-largetype-ASCII.png)

This is a subset of my Large Type Pieces font, but instead of using Unicode 16.0 characters, it uses the legacy alternate character set
found on HP 2640 Series terminals and compatibles.
This is used to create large type text on terminals that support an alternate character set for its ASCII characters.

SoftFonts (Soft Character Sets / DRCS) providing the Larget Type Pieces to DEC VT220, VT320, and VT420 terminals can be found in [my SoftFonts
collections](https://github.com/PhMajerus/Documents).

Note the character set must be selected and then restored when using this FIGfont, for example:
`echo -ne "\e( L"; figlet -f phm-largetype-ASCII -C utf8 "Hello, world!"; echo -ne "\e(B"`


### phm-lcdmatrix
![phm-lcdmatrix](images/phm-lcdmatrix.png)

This font uses Unicode 16.0 octants characters to create a monospaced retro low-rez font like on LCD and LED signboards, and 8-bit computers.
The characters are 6×8 pseudo-pixels, inspired by the Motorola MC6847 character generator, Tatung Einstein TC-01, TRS-80, and other computers of the 1980's.

It does not require an ANSI/VT terminal (does not use escape sequences) and works fine with FIGlet, but the terminal must support the octants characters.


### phm-c64
![phm-c64](images/phm-c64.png)

This font uses Unicode 16.0 octants characters to recreate the original Commodore 64 character set as a large font.
The characters are 8×8 pseudo-pixels, rendered as 4×2 octants characters. It uses two rows and only includes characters originally found in the Commodore 64 chargen ROM. This means a few ASCII characters are missing, as PETSCII was based on an early version of ASCII.

It does not require an ANSI/VT terminal (does not use escape sequences) and works fine with FIGlet, but the terminal must support the octants characters.

_Remember to use `figlet -f phm-c64 -C utf8` to access Unicode characters._


### phm-cga
![phm-cga](images/phm-cga.png)

This font uses Unicode 16.0 octants characters to recreate the original IBM CGA bold character set as a large font. It is one of the original font for the launch of the IBM PC.
The characters are 8×8 pseudo-pixels, rendered as 4×2 octants characters. It uses two rows and supports codepage 437.

It does not require an ANSI/VT terminal (does not use escape sequences) and works fine with FIGlet, but the terminal must support the octants characters.

_Remember to use `figlet -f phm-cga -C utf8` to access Unicode characters._


### phm-vga
![phm-vga](images/phm-vga.png)

This font uses Unicode 16.0 octants characters to recreate the original IBM VGA and MS-DOS CP437 character set for 80 columns × 25 lines mode as a large font. This is probably the font most people remember as the MS-DOS font.
The characters are 8×16 pseudo-pixels, rendered as 4×4 octants characters. It uses four rows and supports codepage 437.

It does not require an ANSI/VT terminal (does not use escape sequences) and works fine with FIGlet, but the terminal must support the octants characters.

_Remember to use `figlet -f phm-vga -C utf8` to access Unicode characters._

### phm-vga-square
![phm-vga-square](images/phm-vga-square.png)

Similar to phm-vga above, but based on the 80 columns × 50 lines mode, which are square characters.
The characters are 8×8 pseudo-pixels, rendered as 4×2 octants characters. It uses two rows and supports codepage 437.

It does not require an ANSI/VT terminal (does not use escape sequences) and works fine with FIGlet, but the terminal must support the octants characters.

_Remember to use `figlet -f phm-vga-square -C utf8` to access Unicode characters._


### phm-dosv
![phm-dosv](images/phm-dosv.png)

This font uses Unicode 16.0 octants characters to recreate the original Microsoft Japanese DOS/V character set.
This is the font used on Japanese versions of IBM PC-DOS and MS-DOS with support for code page 932 (Shift-JIS).
Just like phm-vga above is probably the font most people remember as the MS-DOS font, this is the one Japanese users remember.
The characters are 8×16 pseudo-pixels for half-width and 16×16 pseudo-pixels for full-width, rendered as 4×4 and 8×4 octants characters respectively. It uses four rows and supports codepage 932.

For people not familiar with DOS/V, it contained a special text-mode display driver as well as a software font to be able to render multi-byte character sets (MBCS) such as CP932. This made it possible to support thousands of ideographs (kanji) required by JIS X 0208.
This font is based on the original glyphs from `ANK16.FNT` and `KANJI16.FNT`, which together make the Japanese software font from MS-DOS 6.2/V, and contains all of the characters supported by CP932. This might just make it the largest FIGlet font ever, as it contains 7524 characters!

It does not require an ANSI/VT terminal (does not use escape sequences) and works fine with FIGlet, but the terminal must support the octants characters.

_Remember to use `figlet -f phm-dosv -C utf8` to access Unicode characters._


### phm-shinonome
![phm-shinonome](images/phm-shinonome.png)

This font uses Unicode 16.0 octants characters to display the Shinonome12/東雲12 (Shinonome 12dot) bitmap font, originally designed by Yasuyuki Furukawa / 古川 泰之様 and generously released into the public domain.
The characters are 6×12 pseudo-pixels for half-width and 12×12 pseudo-pixels for full-width, rendered as 3×3 and 6×3 octants characters respectively. It uses three rows and supports ISO 8859-1 (Latin 1), JIS X 0201, and JIS X 0208, which also contains basic Greek and Cyrillic.

It does not require an ANSI/VT terminal (does not use escape sequences) and works fine with FIGlet, but the terminal must support the octants characters.

_Remember to use `figlet -f phm-shinonome -C utf8` to access Unicode characters._


### phm-blocky
![phm-blocky](images/phm-blocky.png)

This font uses extended ASCII characters from the US (437) codepage and ANSI/VT escape sequences for inverted (negative) characters.
It uses just two rows and supports the base ASCII characters set.

It works in FIGlet 2.2.5, but the width computation gets confused, so it can only be used for single lines. It requires `-w 9999` to avoid misplaced line breaks.
It does not work at all in TOIlet 0.3, as escape sequences get removed.

_Remember to use `figlet -f phm-blocky -w 9999` to avoid misplaced line breaks and broken VT control sequences due to bad width computation._


### phm-blocky-reverse
![phm-blocky-reverse](images/phm-blocky-reverse.png)

This font uses extended ASCII characters from the US (437) codepage.
It uses four rows and supports the base ASCII characters set.

Unlike phm-blocky, this reverse version does not require an ANSI/VT terminal (does not use escape sequences) and works fine with FIGlet, but the terminal must support the block elements found in codepage 473.
The equivalent font in non-reverse is not possible without help from ANSI/VT to invert (negative) some characters.


### phm-rounded
![phm-rounded](images/phm-rounded.png)

This font uses Unicode characters (Box Drawings lines, half lines, diagonals and arcs).
It uses four rows and supports the base ASCII characters set.


### phm-slanted
![phm-slanted](images/phm-slanted.png)

This font uses Unicode 13.0 smooth mosaic and sextant characters.
It uses six rows and supports the ASCII, ISO 8859-1 and Windows 1252 Latin-1 characters sets.

_Remember to use `figlet -f phm-slanted -C utf8` to access Unicode characters._


### phm-chisel
![phm-chisel](images/phm-chisel.png)

This font uses Unicode 13.0 smooth mosaic and sextant characters, as well as some quadrants, and requires 16 colors ANSI/VT escape sequences support, and uses six rows.
It contains 629 characters, and supports the ASCII, ISO 8859-1 and Windows 1252 Latin-1 characters sets, and Japanese Katakana (and Hiragana as Katakana).

It works in FIGlet 2.2.5, but the width computation gets confused, so it can only be used for single lines. It requires `-w 9999` to avoid misplaced line breaks.
It does not work at all in TOIlet 0.3, as escape sequences get removed.

Note you can use the [`sed` (stream editor) utility](https://en.wikipedia.org/wiki/Sed) to replace colors.
The font uses colors `97` and `107` for highlight, `37` and `47` for light, and `90` and `100` for shadow. Always set both foreground and background colors of the same brightness to the same color.
The following set of replacements will change the 3 original grays to red (`31` and `41`), green (`32` and `42`), and yellow/brown (`33` and `43`):
```bash
hostname | figlet -f phm-chisel -C utf8 -w 9999 -n | sed -e 's/97/31/g;s/107/41/g;s/37/32/g;s/47/42/g;s/90/33/g;s/100/43/g'
```
<p><details><summary>
It is also possible to use 256-colors or 24-bit colors for finer control.
Here are replacements commands for common colors gradients using the 256-colors palette:

_(Expand for commands to use for red, green, blue, yellow, purple, cyan, orange, pink, and silver color schemes.)_
</summary>

| Color | Command |
|---|---|
| Red | `sed -e 's/97/38;5;210/g;s/107/48;5;210/g;s/37/38;5;167/g;s/47/48;5;167/g;s/90/38;5;124/g;s/100/48;5;124/g'` |
| Green | `sed -e 's/97/38;5;120/g;s/107/48;5;120/g;s/37/38;5;77/g;s/47/48;5;77/g;s/90/38;5;34/g;s/100/48;5;34/g'` |
| Blue | `sed -e 's/97/38;5;103/g;s/107/48;5;103/g;s/37/38;5;61/g;s/47/48;5;61/g;s/90/38;5;19/g;s/100/48;5;19/g'` |
| Yellow | `sed -e 's/97/38;5;228/g;s/107/48;5;228/g;s/37/38;5;185/g;s/47/48;5;185/g;s/90/38;5;142/g;s/100/48;5;142/g'` |
| Purple | `sed -e 's/97/38;5;212/g;s/107/48;5;212/g;s/37/38;5;170/g;s/47/48;5;170/g;s/90/38;5;127/g;s/100/48;5;127/g'` |
| Cyan | `sed -e 's/97/38;5;123/g;s/107/48;5;123/g;s/37/38;5;80/g;s/47/48;5;80/g;s/90/38;5;37/g;s/100/48;5;37/g'` |
| Orange | `sed -e 's/97/38;5;215/g;s/107/48;5;215/g;s/37/38;5;208/g;s/47/48;5;208/g;s/90/38;5;130/g;s/100/48;5;130/g'` |
| Pink | `sed -e 's/97/38;5;218/g;s/107/48;5;218/g;s/37/38;5;211/g;s/47/48;5;211/g;s/90/38;5;168/g;s/100/48;5;168/g'` |
| Silver | `sed -e 's/97/38;5;231/g;s/107/48;5;231/g;s/37/38;5;188/g;s/47/48;5;188/g;s/90/38;5;145/g;s/100/48;5;145/g'` |

</details></p>

_Remember to use `figlet -f phm-chisel -C utf8 -w 9999` to access Unicode characters and to avoid misplaced line breaks and broken VT control sequences due to bad width computation._


### beyond-blue
![beyond-blue](images/beyond-blue.png)

This font was designed by Strahd(ST) & Roy/SAC as `BEYONDX.TDF` for TheDRAW, an MS-DOS ANSI-art drawing application.
I converted it to a FIGlet font from the original file.
It uses characters from the US (437) codepage and ANSI/VT escape sequences for colors to create large colorful 9-rows characters.

The original TDF file contained several color schemes, but I only converted the blue one for now, as it is mostly intended as a historical reference for my own Beyond Neo font below.

It works in FIGlet 2.2.5, but the width computation gets confused, so it can only be used for single lines. It requires `-w 9999` to avoid misplaced line breaks.
It does not work at all in TOIlet 0.3, as escape sequences get removed.

_Remember to use `figlet -f beyond-blue -w 9999` to avoid misplaced line breaks and broken VT control sequences due to bad width computation._


### PHM Beyond Neo (FIGfont family)

This font family is inspired by the look of ST+Roy/SAC Beyond, but using just 5 rows by taking advantage of Unicode 16.0 Symbols for Legacy Computing. It contains 2630 characters, and supports the ASCII, ISO 8859-1 and Windows 1252 Latin-1 characters sets, Greek, Cyrillic, Japanese Katakana (and Hiragana as Katakana), 120 ideographs (mostly for dates, times, places, and numbers in Chinese numerals), 228 color symbols and emojis, and more.
Several versions are available with different color schemes or compatible with plain-text.

#### phm-beyondneo-red; -green; -blue; -yellow; -purple; -cyan; -orange, -pink, -silver, -gold
![phm-beyondneo-colors](images/phm-beyondneo-colors.png)

These are the red, green, blue, yellow, purple, cyan, orange, pink, silver, and gold color schemes of Beyond Neo.
They require 256 colors ANSI/VT escape sequences support.

They work in FIGlet 2.2.5, but the width computation gets confused, so they can only be used for single lines.
They require `-w 9999` to avoid misplaced line breaks.
They do not work at all in TOIlet 0.3, as escape sequences get removed.

If the background color is close to white, the grays can be shifted to go from light gray to black instead of white to dark gray using the [`sed` (stream editor) utility](https://en.wikipedia.org/wiki/Sed).
```bash
figlet -f phm-beyondneo-gold -C utf8 -w 9999 "Test" | sed -e 's/38;5;59/38;5;16/g;s/48;5;59/48;5;16/g;s/38;5;102/38;5;59/g;s/48;5;102/48;5;59/g;s/38;5;145/38;5;102/g;s/48;5;145/48;5;102/g;s/38;5;188/38;5;145/g;s/48;5;188/48;5;145/g;s/38;5;231/38;5;188/g;s/48;5;231/48;5;188/g'
```

_Remember to use `figlet -f phm-beyondneo-red -C utf8 -w 9999` to access Unicode characters (including ISO 8859-1) and to avoid misplaced line breaks and broken VT control sequences due to bad width computation._

#### phm-beyondneo-mono
![phm-beyondneo-mono](images/phm-beyondneo-mono.png)

This is the monochrome version of Beyond Neo. it is designed without any ANSI/VT escape sequence, making it compatible with plain-text and VT-unaware utilities.

_Remember to use `figlet -f phm-beyondneo-mono -C utf8` to access Unicode characters (including ISO 8859-1)._


## Using & installing FIGfonts
You'll need the FIGlet utility, so start with `sudo apt install figlet` or equivalent for your distro.
FIGfonts can be used as it by specifying their paths:
```bash
echo 'Hello, world!' | figlet -f /some_path/phm-largetype.flf -C utf8
```
The `-C utf8` option makes it support Unicode characters, handling the input as UTF-8.

But to make it cleaner and easier to use regularly, the font files can be copied to the FIGfont folder:
```bash
# Find out which directory contains figfonts
figlet -I2
# Copy font file(s) to that directory
sudo cp phm-largetype.flf /usr/share/figlet/phm-largetype.flf
# Use the FIGfont without having to specify the path or extension
echo 'Hello, world!' | figlet -f phm-largetype -C utf8
```

Note many of my fonts use ANSI/VT control sequences, which FIGlet does not support, making it miscalculate the width of characters. The workaround is to use the `-w 9999` argument to prevent it from wrapping text.
To create text that spans several lines, the `fold` utility can be used to prepare the text in advance.
For example:
```bash
uname -a | fold -sw 20 | figlet -f phm-beyondneo-red -w 9999 -C utf8
```
This takes the output of `uname`, formats it for lines of 20 characters max, breaking it at spaces instead of in words, then uses `figlet` to convert that to large colorful characters.

If you want to use only uppercase or lowercase letters from a font that supports both, convert the text in advance.
For example:
```bash
date | tr [:lower:] [:upper:] | figlet -f phm-slanted -w 130 -C utf8
date | tr [:upper:] [:lower:] | figlet -f phm-slanted -w 130 -C utf8
```

---

-- Philippe Majerus, October 2024 to June 2025

---

If you enjoy ANSI-art and Unicode semigraphics, also check out [my cowsay files collection](https://github.com/PhMajerus/CowFiles).

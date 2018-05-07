# monomacs
A Unicode bitmapped font for programmers inspired by Terminal, Proggy and
X11's Fixed.

Current version is **3.300**.

## License ##

Monomacs is licensed under the SIL Open Font License (OFL) 1.1. See LICENSE.
It comes with absolutely no warranty, express or implied.

## Status ##

Note: Monomacs is currently still under active development and is probably
filled with bugs both trivial and major. Use at your own discretion.

## Compatibility ##
Monomacs is compatible with all Unix and Unix-like systems that support BDF.
It is not compatible with any version of Windows.

## Description ##
Monomacs is a bitmapped programming font designed for extended use on both
graphical and non-graphical terminals. Monomacs exhibits all the hallmarks of
fit-for-purpose programming fonts in:

* clearly disambiguating between easily confused characters like 1lI, or O0o;

* punctuation being geared towards use primarily as operators: the asterisk and
  tilde brought closer to the baseline (* ~) to harmonise with the other, more
  traditional operators;
  
* featuring gracious letter-forms with an emphasis on simplification for easier
  reading over long periods of time;
  
* and possessing excellent clarity at small sizes, which aids in maximising
  buffer real-estate, both vertically (small leading) and horizontally
  (close spacing).
  
## Formats ##
Monomacs is currently available in one format (.bdf), point size (13 @ 75 dpi),
and one weight (regular). 

A bold weight is not anticipated because most X11 programs are capable of
automatic boldening under FreeType 2. 

An italic weight is likewise not anticipated because italicised bitmaps tend to
be substandard, and because like the previous point, FreeType 2 is capable of 
automatically italicising them in a somewhat more graceful manner than could be
achieved by anything short of conversion to outline formats.

A .psf variant for use in the Linux or *BSD consoles may be considered in the
near future, when the majority of the font's ranges is completed. .ttf formats
are not planned but you are welcome to convert them to any format you desire.

## Ranges ##
Monomacs contains around 2 652 characters of the Unicode Basic Multilingual Plane.
Although designed primarily as a programming font, it is nevertheless well 
suited to technical writing, such as found in mathematics or linguistics. 

Current ranges are:
* Basic Latin (complete)
* Latin-1 Supplement (complete)
* Latin Extended-A (complete)
* Latin Extended-B (complete)
* IPA Extensions (complete)
* Spacing Modifier Letters (complete)
* Combining Diacritical Marks (partially complete)
* Modern Greek (complete)
* Cyrillic (complete)

## Future developments ##

The inclusion of the Cyrillic, polytonic Greek, Armenian, Georgian and Hebrew 
scripts, as well are mathematical and special-use symbols.

## Installation ##

The following instructions should work for Debian GNU/Linux, Arch Linux and Ubuntu.
If your distribution has bitmap fonts disabled you have two options available to
you: you can can reenable them globally or enable only Monomacs for use in
X11 applications. This guide provides instructions for the latter.

Place Monomacs-13.bdf in either your ~/.fonts directory for your own use,
or /usr/share/fonts for all users. Before you can use it you have to whitelist it
so that X11 knows to use it.

Visit a new file:

``` bash
$ sudo touch /etc/fonts/conf.d/50-enable-monomacs.conf

```

and write the following to it:


``` xml
<!DOCTYPE fontconfig SYSTEM "fonts.dtd">
<fontconfig>
  <selectfont>
    <acceptfont>
      <pattern>
        <patelt name="family"><string>monomacs</string></patelt>
      </pattern>
    </acceptfont>
  </selectfont>
</fontconfig>

```
Finally, update your font cache to make it available for use:

``` bash
$ fc-cache -vf 
```

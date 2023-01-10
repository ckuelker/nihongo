---
title: Directory nihongo/share/katakana
author: Christian Külker
date: 2023-01-10
version: 0.1.4

---

# Directory nihongo/share/katakana Aim

Japanese resources to share for building a Katakana book

# Name Schema for PDF Graphic Files

Most PDF graphic files in this directory are created via `katakana.svg` by
inkscape (version 0.48.5 r10040 - or similar (Debian Wheezy, Jessie). Some
other files in `nihongo/share/i` too. As the resolution of `katakana.svg`
depends on the desktop and the inkscape application (as of now 2023-01-10) it
is recommended to use Debian GNU/Linux 8.11 (jessie) to make changes to
`katakana.svg`.

As far as known the export resolution of inkscape v0.48 under Debian 8.11 is
90dpi, while the export/import resolution of inkscape v1.0.2 under Debian 11.6
(bullseye) is 96dpi. A conversion of the file from inkscape v0.48 to v1.0.2 was
not successful so far.

     ad.pdf     - [a]rrow [d]own
     ag.pdf     - katakana [a] [gray]
     a.pdf      - katakana [a]
     ar.pdf     - [a]rrow [r]ight
     as.pdf     - katakana [a] [s]stroke marks
     at.pdf     - katakana [a] [t]table position

     eg.pdf     - katakana [e] [g]ray
     e.pdf      - katakana [e]
     es.pdf     - katakana [e] [s]troke marks
     et.pdf     - katakana [e] [t]table position

     ig.pdf     - analogue to e
     i.pdf
     is.pdf
     it.pdf

     og.pdf     - analogue to e
     o.pdf
     os.pdf
     ot.pdf

     s.pdf      - [s]pace

     ug.pdf     - analogue to e
     u.pdf
     us.pdf
     ut.pdf

# Process

     1 open: inkscape katakana.svg
     2 change an object (ungroup)
     3 group an object
     4 set group ID via object properties
     5 save katakana.svg (CTRL s)
     6 save copy PDF and choose name to save and object ID
       - Restrict to PDF version 1.5
       - Convert texts to path (include correct fonts!)
       - Rasterzise filter effects
       - Resolution for rasterrization 600dpi
       - Export area is drawing
       - Limit export to the object ID [<INSERT ID HERE>]

## History

| Version | Date       | Notes                                                |
| ------- | ---------- | ---------------------------------------------------- |
| 0.1.4   | 2023-01-10 | Additional info about dpi                            |
| 0.1.3   | 2022-06-23 | History, improve info about dependencies             |
| 0.1.2   | 2020-01-12 | Add hint for inkscape version                        |
| 0.1.1   | 2014-08-24 | Improve info about file saving                       |
| 0.1.0   | 2014-08-24 | Initial release                                      |

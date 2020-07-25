---
title: INSTALL.md
author: Christian Külker
date:  2020-07-25
---

![Github license](https://img.shields.io/github/license/ckuelker/nihongo.svg)
![Github issues](https://img.shields.io/github/issues/ckuelker/nihongo.svg?style=popout-square)
![Github code size in bytes](https://img.shields.io/github/languages/code-size/ckuelker/nihongo.svg)
![Git repo size](https://img.shields.io/github/repo-size/ckuelker/nihongo.svg)
![Last commit](https://img.shields.io/github/last-commit/ckuelker/nihongo.svg)

# Installation

This document describes mainly the installation of the dependencies to create
the PDF documents. The PDF documents by itself can be create via a `Makefile`
in the source directory mentioned in the [README](README.md) after the
dependencies are installed.

## nihongo-0.1.2

### Operating System

Debian Buster, Unicode 10 and at least XaLaTex 2018.20190227-2 is needed.

### Dependencies

In addition to the instructions of nihongo-0.1.1 install the font Hanazono
Mincho. This font is used for Henteigana. Also the font `YOzAb` is needed and
provided in `fonts-yozvox-yozfont`. The font `AoyagiSosekiFont2` is needed,
provided by `fonts-aoyagi-soseki`. The font `KanjiStrokeOrders` is provided by
`fonts-kanjistrokeorders`. The font `KouzanBrushFontGyousyo` is provided by
`fonts-kouzan-mouhitsu`.

```shell
aptitude install fonts-hanazono fonts-yozvox-yozfont fonts-aoyagi-soseki \
fonts-kanjistrokeorders fonts-kouzan-mouhitsu
```

### Known Issues

Due to the lack of Unicode 10 support, not all glyphs from the Hentaigana
table are printed.

## nihongo-0.1.1

### Operating System

Debian Buster was used for testing.

### Dependencies

#### multind.sty

While `multind.sty` is available in `texlive-latex-extra` under Wheezy it has
been removed in recent LaTeX releases. The source has to be changed:

The old command `\bf` has to be changed to `\textbf`.

~~~
cd nihongo/katakana
wget https://ctan.org/tex-archive/macros/latex209/contrib/misc/multind.sty
sed -i -e 's%\\bf\s\+%\\textbf %g' multind.sty
~~~

#### ruby.sty

    aptitude install latex-cjk-all

#### bclogo.sty (texlive-pstricks)

    aptitude install texlive-extra-utils

#### Fonts

The font YoZ changed a lot since 2014. Therefore
`share/preamble/standard-english.tex` was changed too.

    aptitude install fonts-dejima-mincho fonts-yozvox-yozfont fonts-vlgothic\
    fonts-takao-mincho fonts-motoya-l-maruberi fonts-kouzan-mouhitsu \
    fonts-kiloji fonts-ipafont fonts-aoyagi-kouzan-t

Make sure 'non-free' is enabled in `/etc/apt/sources.list` for the
[Mikachan](http://www001.upp.so-net.ne.jp/mikachan/) font.

    aptitude install fonts-mikachan

## nihongo-0.1.0

### Dependencies

#### Operating System

nihongo-0.1.0 uses `eps` and `pdf` as pictures. This do not work well with
newer versions of Debian. The last working version of Debian that is known to
work is Debian Wheezy.

#### LaTeX

nihongo-0.1.0 was tested with a full installation of `texlive`. Maybe a subset
will work too.

    aptitude install texlive-full

#### Fonts

For katakana 0.9 some additional fonts are needed.

    aptitude install fonts-dejima-mincho fonts-yozvox-yozfont

Make sure 'non-free' is enabled in `/etc/apt/sources.list` for the
[Mikachan](http://www001.upp.so-net.ne.jp/mikachan/) font.

    aptitude install fonts-mikachan

#### Perl

The `bin/extract-ifor` script needs the Perl module `Lingua::JA::Sort::JIS`.
Unfortunately there is no package for Wheezy. The module can be installed in
many different ways. One method is to use `cpanminus`.

    aptitude install cpanminus
    cpanm Lingua/JA/Sort/JIS.pm


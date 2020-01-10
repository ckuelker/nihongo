---
title: INSTALL.md
author: Christian Külker
date:  2020-01-09
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


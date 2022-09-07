# +---------------------------------------------------------------------------+
# | Makefile                                                                  |
# |                                                                           |
# | - japanese-script-hiragana-english.pdf                                    |
# | - japanese-script-hiragana-ngerman.pdf                                    |
# | - japanese-script-katakana-english.pdf                                    |
# |                                                                           |
# | Setup language specific parts for make. The language switch is:           |
# |                                                                           |
# |   Shell    Makefile LaTeX    Possible Values                              |
# |   -------- -------- -------- ---------------                              |
# |   $JLANG   JLANG    \jlang   english|ngerman                              |
# |   $JTOPIC  JTOPIC   \jtopic  hiragana|katakana                            |
# |   $JSCRIPT JSCRIPT  \jscript Hiragana|Katakana                            |
# |                                                                           |
# | USAGE:                                                                    |
# |                                                                           |
# |     make JTOPIC   JLANG   <GOAL>                                          |
# |                                                                           |
# | EXAMPLES:                                                                 |
# |                                                                           |
# |     make hiragana english usage                                           |
# |     make hiragana english pdf                                             |
# |     make realclean hiragana english pdf                                   |
# |     make realclean katakana english pdf                                   |
# |     make realclean hiragana ngerman pdf                                   |
# |                                                                           |
# | Changes:                                                                  |
# |                                                                           |
# | 0.1.0 2022-07-08 Christian Külker <c@c8i.org>                             |
# |     - Initial release                                                     |
# |                                                                           |
# +---------------------------------------------------------------------------+
#
# CHANGES in:
#   cfg/hiragana/english/Makefile.in
#   cfg/hiragana/ngerman/Makefile.in
#   cfg/katakana/english/Makefile.in
# -----------------------------------------------------------------------------
# NO CHANGES BEYOND THIS POINT
#
#
include  ../in/Makefile.function.in
# --- [ DEFAULT ] -------------------------------------------------------------
ifndef JTOPIC
JTOPIC:=hiragana
endif
ifndef JSCRIPT
JSCRIPT:=Hiragana
endif
ifndef JLANG
JLANG:=english
endif
#
include cfg/$(JTOPIC)/$(JLANG)/Makefile.in
include ../in/Makefile.in
include ../in/Makefile.jtopic.in
include ../in/Makefile.jlang.in
include ../in/Makefile.jtopic-jlang.in

# USAGE: make  -  to see usage
FILE=japanese-script-katakana
LATEX=xelatex
MKIDX=makeindex -c
TERMS=ListOfJapaneseTechnicalTerms.tex

usage:
ifndef LATEX
	@make E=LATEX N=release T=${FILE}.pdf usage-message
endif
ifndef VERSION
	@make E=VERSION N=release T=${FILE}.pdf usage-message
endif
	@echo "\\\newcommand{\\\jversionN}{${VERSION}}" > VERSION.tex
ifndef DATE
	@make E=DATE N=release T=${FILE}.pdf usage-message
endif
	@echo "\\\newcommand{\\\jdate}{${DATE}}" > DATE.tex


usage-release:
ifndef LATEX
	@make E=LATEX T=release N=${FILE}.pdf usage-message
endif
ifndef VERSION
	@make E=VERSION T=release N=${FILE}.pdf usage-message
endif
	@echo "\\\newcommand{\\\jversion}{${VERSION}}" > VERSION.tex
ifndef DATE
	@make E=DATE T=release N=${FILE}.pdf usage-message
endif
	@echo "\\\newcommand{\\\jdate}{${DATE}}" > DATE.tex


usage-message:
	@echo "====================================================="
	@echo "    ERROR: ${E} was not provided"
	@echo "    USAGE: "
	@echo "        make LATEX=pdflatex VERSION=x.x DATE='January 2014' ${T}"
	@echo "        make LATEX=xelatex  VERSION=x.x DATE='January 2014' ${T}"
	@echo "    TARGETS: all, clean, realclean, backup, ${N}"
	@echo "====================================================="
	@exit 2

all: usage ${FILE}.pdf

VERSION.tex:
	bash -c 'echo "\newcommand{\jversion}{$$VERSION}">VERSION.tex'
DATE.tex:
	bash -c 'echo "\newcommand{\jdate}{$$DATE}">DATE.tex'
rev.dat:
	echo -n 1 > rev.dat

revision.tex: rev.dat
	bash -c 'REV=`cat rev.dat`;let REV++;echo $$REV>rev.dat;echo "\newcommand{\revision}{$$REV}">revision.tex'
${FILE}.pdf: usage ${FILE}.tex  revision.tex VERSION.tex DATE.tex
	bash -c 'echo "\newcommand{\jversion}{$$VERSION}">VERSION.tex'
	bash -c 'echo "\newcommand{\jdate}{$$DATE}">DATE.tex'
	#. /srv/env/perl-5-14-2 && cd .. && bin/extract-ifor && pwd && cp $(TERMS) share/chap && rm -f $(TERMS)
	cd .. && bin/extract-ifor && pwd && cp $(TERMS) share/chap && rm -f $(TERMS)
	${LATEX} ${FILE}.tex
	${MKIDX} english.idx
	#${MKIDX} -g german.idx TODO: fix wrong quote in index, should not be "
	${MKIDX} german.idx
	${MKIDX} japanese.idx
	${LATEX} ${FILE}.tex
	${LATEX} ${FILE}.tex
	bash -c 'REV=`cat rev.dat`;let REV++;echo $$REV>rev.dat;echo "\newcommand{\revision}{$$REV}">revision.tex'
	cat ${FILE}.log|grep Warning
clean:
	rm -f *.jtoc *.idx *.ilg *.ind *.toc *.vrb *.nav *.aux *.log *.svn *.snm *.out *~ VERSION.tex DATE.tex revision.tex

realclean: clean
	rm -f *.pdf
test-release:
	@if [ -d ${VERSION} ]; then echo "ERROR: release '${VERSION}' already there, remove before proceed!";exit 254; fi
release: test-release usage-release all
	mkdir -p ${VERSION}
	cp ${FILE}.pdf ${VERSION}/${FILE}-v${VERSION}.pdf
	cp ${FILE}.tex ${VERSION}/${FILE}-v${VERSION}.tex
	make realclean
	# reprocess with gs: embedd fonts, smaller
	gs -sDEVICE=pdfwrite -dCompatibilityLevel=1.4 -dNOPAUSE -dQUIET \
	     -dSubsetFonts=true -dEmbedAllFonts=true -dMaxSubsetPct=100 \
	     -dBATCH -sOutputFile=${VERSION}/${FILE}-v${VERSION}-gs.pdf ${VERSION}/${FILE}-v${VERSION}.pdf

.PHONY: all
all: psychology.pdf

SRC+=		psychology.tex abstract.tex bibliography.bib
SRC+= 		contents.tex

FIGURES+= 	citations.png

psychology.pdf: ${SRC} ${FIGURES} beamer-didactic.sty

citations.png:
	wget -O $@ http://imgs.xkcd.com/comics/citations.png


beamer-didactic.sty: ../beamer-didactic/beamer-didactic.sty
	${LN} $< $@

../beamer-didactic/%:
	${MAKE} -C $(dir $@) $(notdir $@)


.PHONY: all
all: README.md

README.md: video.md abstract.md
	echo "# Psychology" > $@
	${CAT} $^ >> $@

TEX2MDFLAGS=	-s -t markdown_strict --bibliography bibliography.bib

abstract.md: abstract.tex bibliography.bib
	${CONVERT.tex.md}


.PHONY: clean
clean:
	${RM} psychology.pdf
	${MAKE} -C ../beamer-didactic clean

.PHONY: distclean
distclean:
	${RM} citations.png
	${MAKE} -C ../beamer-didactic distclean


INCLUDE_MAKEFILES=../makefiles
include ${INCLUDE_MAKEFILES}/tex.mk
include ${INCLUDE_MAKEFILES}/doc.mk

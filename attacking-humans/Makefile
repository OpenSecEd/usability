.PHONY: all
all: attacking-humans.pdf README.md

SRC+=		attacking-humans.tex abstract.tex bibliography.bib
SRC+= 		contents.tex

FIGURES+= 	security.png

attacking-humans.pdf: ${SRC} ${FIGURES} beamer-didactic.sty

security.png:
	wget -O $@ http://imgs.xkcd.com/comics/security.png 

beamer-didactic.sty: ../beamer-didactic/beamer-didactic.sty
	${LN} $< $@

../beamer-didactic/%:
	${MAKE} -C $(dir $@) $(notdir $@)


.PHONY: all
all: README.md

README.md: video.md abstract.md
	echo "# Attacking humans" > $@
	${CAT} $^ >> $@

TEX2MDFLAGS=	-s -t markdown_strict --bibliography bibliography.bib

abstract.md: abstract.tex bibliography.bib
	${CONVERT.tex.md}


.PHONY: clean
clean:
	${RM} attacking-humans.pdf
	${MAKE} -C ../beamer-didactic clean

.PHONY: distclean
distclean:
	${RM} security.png
	${MAKE} -C ../beamer-didactic distclean


INCLUDE_MAKEFILES=../makefiles
include ${INCLUDE_MAKEFILES}/tex.mk
include ${INCLUDE_MAKEFILES}/doc.mk

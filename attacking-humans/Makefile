.PHONY: all
all: attacking-humans.pdf

SRC+=		attacking-humans.tex abstract.tex attacking-humans.bib
SRC+= 		contents.tex

FIGURES+= 	security.png

attacking-humans.pdf: ${SRC} ${FIGURES} beamer-didactic.sty

security.png:
	wget -O $@ http://imgs.xkcd.com/comics/security.png 

beamer-didactic.sty: ../beamer-didactic/beamer-didactic.sty
	${LN} $< $@

../beamer-didactic/%:
	${MAKE} -C $(dir $@) $(notdir $@)


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

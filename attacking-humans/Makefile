.PHONY: all
all: attacking-humans.pdf

SRC+=		attacking-humans.tex abstract.tex attacking-humans.bib
SRC+= 		contents.tex

FIGURES+= 	security.png

attacking-humans.pdf: ${SRC} ${FIGURES}

security.png:
	wget -O $@ http://imgs.xkcd.com/comics/security.png 


.PHONY: clean
clean:
	${RM} attacking-humans.pdf


.PHONY: distclean
distclean:
	${RM} security.png


INCLUDE_MAKEFILES=../makefiles
include ${INCLUDE_MAKEFILES}/tex.mk

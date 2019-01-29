.PHONY: all
all: attacking-humans.pdf

SRC+=		attacking-humans.tex abstract.tex attacking-humans.bib
SRC+= 		contents.tex

FIGURES+= 	security.png

DEPENDS+= 	../beamer-didactic/beamer-didactic.sty

attacking-humans.pdf: ${SRC} ${FIGURES} ${DEPENDS}

security.png:
	wget -O $@ http://imgs.xkcd.com/comics/security.png 

${DEPENDS}:
	${MAKE} -C $(dir $@) $(notdir $@)
	${LN} $@


.PHONY: clean
clean:
	${RM} attacking-humans.pdf


.PHONY: distclean
distclean:
	${RM} security.png
	$(foreach f,$(notdir ${DEPENDS}),${RM} $f;)
	$(foreach d,$(dir ${DEPENDS}),${MAKE} -C $d clean distclean;)


INCLUDE_MAKEFILES=../makefiles
include ${INCLUDE_MAKEFILES}/tex.mk

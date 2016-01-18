.PHONY: all
all: overview.pdf

SRC=		overview.tex abstract.tex overview.bib

FIGURES= 	security.png
FIGURES+= 	citations.png
FIGURES+= 	password_strength.png
FIGURES+= 	pet_security_question.png

overview.pdf: ${SRC} ${FIGURES}

security.png:
	wget -O $@ http://imgs.xkcd.com/comics/security.png 

citations.png:
	wget -O $@ http://imgs.xkcd.com/comics/citations.png

password_strength.png:
	wget -O $@ http://imgs.xkcd.com/comics/password_strength.png

pet_security_question.gif:
	wget -O $@ http://safr.kingfeatures.com/idn/cnfeed/zone/js/content.php?file=aHR0cDovL3NhZnIua2luZ2ZlYXR1cmVzLmNvbS9CaXphcnJvLzIwMTIvMDkvQml6YXJyb19wLjIwMTIwOTI3XzYxNi5naWY=

pet_security_question.png: pet_security_question.gif
	convert $^ $@

password_reuse.png:
	wget -O $@ http://imgs.xkcd.com/comics/password_reuse.png


.PHONY: clean-depends
clean-depends:
	${RM} security.png citations.png password_strength.png
	${RM} pet_security_question.gif pet_security_question.png
	${RM} password_reuse.png


INCLUDE_MAKEFILES=../makefiles
include ${INCLUDE_MAKEFILES}/tex.mk

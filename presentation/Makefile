
BASE := present_withR

# R settings
R := R
ROPTS := --slave --no-save --no-restore

${BASE}.pdf:	${BASE}.tex
	texi2pdf --batch $<
# texi2pdf is part of the texinfo package: sudo apt-get install texinfo

${BASE}.tex:	${BASE}.Rnw
	@echo "library('knitr'); knit('$<')" | ${R} ${ROPTS}

clean:
	rm -f $(addprefix ${BASE}.,aux bbl blg log nav out snm toc vrb tex)

cleanall: clean
	rm -f plots/* .cache/*

.PHONY: clean cleanall




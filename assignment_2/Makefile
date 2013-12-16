NAME="assignment_2"
PICS_SVG=`ls images/*.svg`
PICS_PNG=`ls images/*.png`
PICS_JPG=`ls images/*.jpg`

all : latex

.PHONY:clean
clean :
	rm -f *.aux *.bcf *.blg *.bbl *.log *.pdf *.toc *.dvi *.out *.bcf *.run.xml contents/*.aux
	find -name '*~' -exec rm {} \;

.PHONY:latex
latex : 
	pdflatex ${NAME}.tex
	biber ${NAME}
	pdflatex ${NAME}.tex
	pdflatex ${NAME}.tex

.PHONY:images
images :
	for i in $(PICS_SVG); do inkscape -z $$i -A `echo $$i | sed 's/\(.*\.\)svg/\1pdf/'`; done
	for i in $(PICS_PNG); do convert $$i `echo $$i | sed 's/\(.*\.\)png/\1pdf/'`; done
	for i in $(PICS_JPG); do convert $$i `echo $$i | sed 's/\(.*\.\)jpg/\1pdf/'`; done

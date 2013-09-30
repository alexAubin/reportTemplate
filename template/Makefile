MAIN = main
TITLE = title
TEX = latex -interaction=nonstopmode
ERROR_PARSING = grep "\\\.box\|\!\|^l\.\|^  " 1>&2

pdf : $(MAIN).pdf

title.pdf : ../$(TITLE).tex
	$(TEX) $(TITLE).tex | $(ERROR_PARSING); dvipdf $(TITLE).dvi $(TITLE).pdf;

$(MAIN).pdf : $(TITLE).pdf $(MAIN).tex ../report.tex 
	$(TEX) $(MAIN).tex | $(ERROR_PARSING); dvipdf $(MAIN).dvi $(MAIN).pdf; mv $(MAIN).pdf ../report.pdf
#	$(TEX) $(MAIN).tex | $(ERROR_PARSING); dvipdf $(MAIN).dvi $(MAIN).pdf; pdfunite $(TITLE).pdf $(MAIN).pdf ../report.pdf

clean :
	rm -f *.aux *.log *.out *.dvi *.pdf

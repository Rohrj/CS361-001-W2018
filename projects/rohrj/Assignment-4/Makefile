TARGET=WellLiv-DIS

# default: pdf

all: $(TARGET).pdf

#bib: bib
 	#bibtex ${TARGET}

# dvi: ${TARGET}.tex 
# #	run latex twice to get references correct
# 	latex ${TARGET}.tex
# #	you can also have a bibtex line here
# 	# bibtex $(TARGET)
# 	latex $(TARGET).tex

# ps: dvi
# 	dvips -R -Poutline -t letter ${TARGET}.dvi -o ${TARGET}.ps

# pdf: ps
# 	ps2pdf ${TARGET}.ps

$(TARGET).pdf: *.tex *.bib
	pdflatex -shell-escape $(TARGET).tex
	pdflatex -shell-escape $(TARGET).tex
	#makeindex $(TARGET)
	bibtex $(TARGET)
	pdflatex -shell-escape $(TARGET).tex
	pdflatex -shell-escape $(TARGET).tex

clean-dvi:
	rm -f ${TARGET}.aux
	rm -f ${TARGET}.log
	rm -f ${TARGET}.dvi
	rm -f ${TARGET}.out
	rm -f ${TARGET}.toc

clean-ps: clean-dvi
	rm -f ${TARGET}.ps

clean-pdf: clean-ps
	rm -f ${TARGET}.bbl
	rm -f ${TARGET}.blg
	rm -f ${TARGET}.pdf


clean: clean-pdf

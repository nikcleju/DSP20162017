PANDOC = pandoc
IFORMAT = markdown

pdf: 
	jupyter nbconvert 0*.ipynb --to pdf
	mv *.pdf export_pdf

slides:
	jupyter nbconvert 0*.ipynb --to slides
	mv *.html export_html

pdfslides: 
	$(PANDOC) -s -f $(IFORMAT)+latex_macros -t beamer -o 03_01_ZTransform.pdf --slide-level 3 --include-in-header macros.md  03_01_ZTransform.md
	
testpdfslides: 
	$(PANDOC) -s -f $(IFORMAT)+latex_macros -t beamer -o 03_01_ZTransform.pdf --slide-level 3 03_01_ZTransform.md

filterout=02_SignalsAndSystems.ipynb
infiles := $(wildcard *.ipynb)
infiles:= $(filter-out $(filterout),$(infiles))
outfiles := $(infiles:.ipynb=.pdf)

beamer: $(outfiles)

$(outfiles): %.pdf : %.ipynb
	jupyter nbconvert --to markdown $<
	pandoc -Ss -t beamer -o $@ $(basename $@).md -V fontsize=8pt 
	mv $@ export_beamer
	#rm $(basename $@).md
	#rm -r $(basename $@)_files
	

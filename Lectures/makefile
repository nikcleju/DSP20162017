pdf: 
	jupyter nbconvert 0*.ipynb --to pdf
	mv *.pdf export_pdf

slides:
	jupyter nbconvert 0*.ipynb --to slides
	mv *.html export_html


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
	

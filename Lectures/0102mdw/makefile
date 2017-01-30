PANDOC = pandoc
IFORMAT = markdown

nbpdf: 
	jupyter nbconvert 0*.ipynb --to pdf
	mv *.pdf export_pdf

nbslides:
	jupyter nbconvert 0*.ipynb --to slides
	mv *.html export_html

mdpdf3: 
	$(PANDOC) -s -f $(IFORMAT)+latex_macros -t beamer -o 03_01_ZTransform.pdf --slide-level 3 --include-in-header macros.md  03_01_ZTransform.md

mdpdf: 
	$(PANDOC) -s -f $(IFORMAT)+latex_macros -t beamer -o 04_FrequencyAnalysisOfDiscreteSignals.pdf --slide-level 3 --include-in-header macros.md  04_FrequencyAnalysisOfDiscreteSignals.md

mdw1pdf: 
	pweave -f pandoc 01_Sampling.mdw
	$(PANDOC) -s -f $(IFORMAT)+latex_macros -t beamer -o 01_Sampling.pdf --slide-level 3 --include-in-header macros.md  01_Sampling.md

mdw2pdf: 
	pweave -f pandoc 02_SignalsAndSystems.mdw
	$(PANDOC) -s -f $(IFORMAT)+latex_macros -t beamer -o 02_SignalsAndSystems.pdf --slide-level 3 --include-in-header macros.md  02_SignalsAndSystems.md

mdw4pdf: 
	pweave -f pandoc 04_FrequencyAnalysisOfDiscreteSignals.mdw
	$(PANDOC) -s -f $(IFORMAT)+latex_macros -t beamer -o 04_FrequencyAnalysisOfDiscreteSignals.pdf --slide-level 3 --include-in-header macros.md  04_FrequencyAnalysisOfDiscreteSignals.md

mdw5pdf: 
	pweave -f pandoc 05_FrequencyAnalysisOfDiscreteSystems.mdw
	$(PANDOC) -s -f $(IFORMAT)+latex_macros -t beamer -o 05_FrequencyAnalysisOfDiscreteSystems.pdf --slide-level 3 --include-in-header macros.md  05_FrequencyAnalysisOfDiscreteSystems.md
	
prep:
	$(PANDOC) -s -f markdown -o ../PreparationForExam.pdf ../PreparationForExam.md
	

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
	

PANDOC = pandoc
IFORMAT = markdown

pdf: 
	jupyter nbconvert 0*.ipynb --to pdf

slides:
	jupyter nbconvert 0*.ipynb --to slides

pdfslides: 
	$(PANDOC) -s -f $(IFORMAT)+latex_macros -t beamer -o 03_01_ZTransform.pdf --slide-level 3 --include-in-header macros.md  slides_header.md 03_01_ZTransform.md

testpdfslides: 
	$(PANDOC) -s -f $(IFORMAT)+latex_macros -t beamer -o 03_01_ZTransform.pdf --slide-level 3 03_01_ZTransform.md


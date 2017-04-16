FILE=code_highlighting.tex

.PHONY: all

all:
	latexmk -pdf -pdflatex="pdflatex -interaction=nonstopmode --shell-escape" -use-make $(FILE)
	latexmk -c
	rm -rf _minted-code_highlighting code_highlighting.mw
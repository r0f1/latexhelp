
# Latex

## Figures

```latex
\begin{figure}[H]
  \centering
  \includegraphics[width=0.5\textwidth]{merging_example}
  \caption{Two collections of records that need to be linked.}
  \label{fig:merging_example}
\end{figure}
```

## Lists

```latex
\usepackage[ampersand]{easylist}

\begin{easylist}[itemize] % default=enumerate
& Main item
&& Sub item
&& Another sub item
\end{easylist}
```
[Source](https://en.wikibooks.org/wiki/LaTeX/List_Structures#Easylist_package)

## Tables
```latex
\usepackage{longtable}

\begin{longtable}[c]{l c c}
\caption{My caption} \\

bla	 & bla & bla \\
bla  & bla & bla \\

\label{tab:baseline} \\
\caption*{The section for footnotes.}
\end{longtable}
```

A more complicated table: [tex](https://github.com/r0f1/latexhelp/blob/master/templates/table1.tex) | [pdf](https://github.com/r0f1/latexhelp/blob/master/templates/table1.pdf). 

## Referencing

```latex
In section~\ref{sec:greetings} we will greet you!

\section{Greetings}
\label{sec:greetings}

Hello!
```

## Citing a Web Resource From Within the Document

 
```latex
\begin{filecontents}{publication.bib}
@misc{caesar2017awesome,
	title={{A}wesome {P}ublic {D}atasets},
	author={caesar0301},
	howpublished = {\url{https://github.com/caesar0301/awesome-public-datasets}},
	note = {Accessed: 2017-01-27}
}
\end{filecontents}

\begin{document}

There is a curated list of awesome datasets~\cite{caesar2017awesome}.

\bibliographystyle{plain}
\bibliography{publication}

\end{document}
```

## Makefile

```make
.PHONY: all clean

all:
	latexmk -pdf -pdflatex="pdflatex -interaction=nonstopmode" -use-make filename.tex
	latexmk -c

clean:
	rm -f filename.bbl publication.bib
```
Requires [proTeXt](https://www.tug.org/protext/) and [Perl](https://www.activestate.com/activeperl/downloads).

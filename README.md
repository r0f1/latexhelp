
# Useful latex code

## Figures

```latex
\begin{figure}[H]
  \centering
  \includegraphics[width=0.5\textwidth]{merging_example}
  \caption{Two collections of records that need to be linked.}
  \label{fig:merging_example}
\end{figure}
```

## Referencing

```latex
\section{Greetings}
\label{sec:greetings}

Hello!

\section{Referencing}

I greeted in section~\ref{sec:greetings}.
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
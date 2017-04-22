
# Latex

## Font Sizes

```latex
\tiny
\scriptsize
\footnotesize
\small
\normalsize
\large
\Large
\LARGE
\huge
\Huge
```

## Figures

```latex
\usepackage{float}
\usepackage{graphicx}

\graphicspath{{./img/}{./pictures/}}

% regular
\begin{figure}[H]
  \centering
  \includegraphics[width=0.5\textwidth]{merging_example}
  \caption{Two collections of records that need to be linked.}
  \label{fig:merging_example}
\end{figure}


% side by side
\usepackage{caption}
\usepackage{subcaption}

\begin{figure}[H]
  \centering
  \begin{subfigure}[b]{0.4\textwidth}
    \includegraphics[width=\textwidth]{flower1.jpg}
    \caption{Flower one.}
    \label{fig:f1}
  \end{subfigure}
  \begin{subfigure}[b]{0.4\textwidth}
    \includegraphics[width=\textwidth]{flower2.jpg}
    \caption{Flower two.}
    \label{fig:f2}
  \end{subfigure}
  \caption{My flowers.}
\end{figure}
```

## Lists

```latex
\usepackage[shortlabels]{enumitem}

% \arabic* generates numbers 1, 2, 3, 4
% a generates letters a, b, c, d
% i generates roman letters i, ii, iii, iv
\begin{enumerate}[(\arabic*)]
\item The load is (or will be) very high
\item The load is (or will be) very low, but greater than zero
\item The load is (or will be) in an acceptable range
\item The load is zero
\end{enumerate}
```
[Source](https://en.wikibooks.org/wiki/LaTeX/List_Structures#Easylist_package)

## Tables
```latex
\usepackage{ctable}
\usepackage{longtable}
\usepackage{array}

\newcolumntype{R}[1]{>{\raggedright\arraybackslash}p{#1}} % p=top m=middle b=bottom alignment
\newcolumntype{L}[1]{>{\raggedleft\arraybackslash}p{#1}}
\newcolumntype{C}[1]{>{\centering\arraybackslash}p{#1}}

\begin{longtable}[c]{l c c}
\caption{My caption} \\

bla & bla & bla \\
\specialrule{.05em}{.3em}{.1em} % {thickness}{upper padding}{lower padding}
bla & bla & bla \\

\label{tab:baseline} \\
\caption*{The section for footnotes.}
\end{longtable}
```

A more complicated table: [tex](https://github.com/r0f1/latexhelp/blob/master/templates/table1.tex) | [pdf](https://github.com/r0f1/latexhelp/blob/master/templates/table1.pdf). 


## Code Listings
```latex
\usepackage{minted}
```
Install python package `pygments` first.  
Compile with `--shell-escape`.

See templates: [tex](https://github.com/r0f1/latexhelp/blob/master/templates/code_highlighting.tex) | [pdf](https://github.com/r0f1/latexhelp/blob/master/templates/code_highlighting.pdf) | [makefile](https://github.com/r0f1/latexhelp/blob/master/templates/makefile).

## Referencing

```latex
In section~\ref{sec:greetings} we will greet you!

\section{Greetings}
\label{sec:greetings}

Hello!
```

## Citing
 
```latex
\begin{filecontents}{publication.bib}
@misc{caesar2017awesome,
	title = {{Awesome Public Datasets}},
	author = {caesar0301},
	howpublished = {\url{https://github.com/caesar0301/awesome-public-datasets}},
	note = {Accessed: 2017-01-27}
},
@article{turing1936computable,
  title={{On computable numbers, with an application to the Entscheidungsproblem}},
  author={Turing, Alan Mathison},
  journal={J. of Math},
  volume={58},
  pages={345--363},
  year={1936}
}
\end{filecontents}

\begin{document}

There is a curated list of awesome datasets~\cite{caesar2017awesome}.

This is a good book page~\cite[p.~16]{turing1936computable}. 
These are also pages~\cite[pp.~150--153]{turing1936computable}.

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

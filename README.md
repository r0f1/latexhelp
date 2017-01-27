
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

## Citing a webresource from within the document

 
```latex
\begin{filecontents}{publication.bib}
@misc{dedupedatasets,
	title={{A}wesome {P}ublic {D}atasets},
	author={caesar0301},
	howpublished = {\url{https://github.com/caesar0301/awesome-public-datasets}},
	note = {Accessed: 2017-01-27}
}
\end{filecontents}

\begin{document}

\bibliographystyle{plain}
\bibliography{publication}

\end{document}
```

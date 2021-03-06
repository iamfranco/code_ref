# LaTeX Reference

#### include graphics
```latex
\begin{center}
  \includegraphics[width=0.8\textwidth]{graphics.eps}
\end{center}
```

#### Configuration for code
```latex
\documentclass[12pt]{article}
\usepackage[title]{appendix}
\usepackage{listings,amsmath,amssymb,xcolor,graphicx,url,natbib,enumitem}
\usepackage[inner=3cm,outer=3cm,top=3cm,bottom=3cm]{geometry}
\definecolor{lgrey}{HTML}{808080}
\definecolor{dgrey}{HTML}{404040}
\definecolor{codegreen}{rgb}{0,0.6,0}
\definecolor{codegray}{rgb}{0.5,0.5,0.5}
\definecolor{codepurple}{rgb}{0.58,0,0.82}
\definecolor{backcolour}{rgb}{0.98,0.98,0.98}

\lstset{
    language=matlab,
    basicstyle=\small\ttfamily,
    backgroundcolor=\color{backcolour},
    commentstyle=\color{codegreen},
    keywordstyle=\color{magenta},
    numberstyle=\tiny\color{codegray},
    stringstyle=\color{codepurple},
    rulecolor=\color{dgrey},
    breakatwhitespace=false,
    breaklines=true,
    captionpos=b,
    keepspaces=true,
    showspaces=false,
    showstringspaces=false,
    showtabs=false,
    tabsize=4,
    numbers=left
}
\newcommand{\vect}[1]{\textbf{#1}}

\def\inline{\lstinline[basicstyle=\ttfamily]}
\newcommand{\includecode}[2]{\subsection{\lstinline[basicstyle=\ttfamily\large]{#1}}\lstinputlisting{#2}}

\title{Document title}
\author{iamfranco}
\date{}

\begin{document}
\maketitle

\end{document}
```

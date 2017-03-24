# iLMbeamer

By Mathieu Leocmach

A $\latex$-beamer class to make bost presentations and posters for Institut Lumière Matière in Lyon.

For a presentation:

```latex
\documentclass[xcolor=table]{beamer}
\usepackage[utf8]{inputenc}
\usepackage[british]{babel}
\mode<presentation>{\usetheme{ilm}}
\begin{document}
\begin{frame}{goodtitle}
  better text
\end{frame}
\end{document}
```

For a poster:
```latex
\documentclass[xcolor=table]{beamer}
\usepackage[orientation=portrait, size=a0, scale=1]{beamerposter}
\usepackage[utf8]{inputenc}
\usepackage[british]{babel}
\mode<presentation>{\usetheme{ilm}}

\colorlet{Main}{ilmorange}
\colorlet{Accent1}{ilmcolor}
\colorlet{Accent2}{ilmcolor!65!black}

% see documentation for a0poster class for the size options here
\let\Textsize\normalsize
\def\Norulehead#1{\noindent\hbox to \hsize{\hfil\LARGE\textcolor{Main}{\textbf{#1}}}\bigskip}
\def\Head#1{\Norulehead{\hrulefill #1}}
\def\LHead#1{\noindent{\Large \color{Accent2}\textbf{#1}}\smallskip}
\def\affiliation#1{\Large \textcolor{Accent2}{\textit{#1}}\smallskip}
\def\Subhead#1{\noindent{\large\color{Accent1}\textbf{#1}}}
\def\Title#1{\noindent{\veryHuge\color{Main}\raggedright\textsf{\textbf{#1}}}}

\setbeamertemplate{headline}{%
	%logo sponsors
	\let\mydim\relax
	\newlength\mydim
	\setlength{\mydim}{0.75cm}
	\rule[-.3\baselineskip]{0pt}{4.5cm}
	\hfill\pgfuseimage{cnrs-logo}\hspace*{\mydim}\pgfuseimage{ucbl-logo}\hspace*{\mydim}
	\includegraphics[height=3cm]{presentation/ENS_Lyon.pdf}\hspace*{\mydim}
	\pgfuseimage{univlyon-logo}\hspace*{\mydim}
	\includegraphics[height=4cm]{presentation/invest-avenir.pdf}\hspace*{\mydim}
	\includegraphics[height=4cm,clip=true, trim=6mm 14mm 6mm 0]{../Yaourt/NEW-Logo-ERC-OUTLINE}\hspace*{\mydim}
	\includegraphics[height=3cm]{presentation/frama.png}\hspace*{\mydim}
	\includegraphics[height=4cm]{presentation/ICL}\hspace*{\mydim}
}

% The textpos package is necessary to position textblocks at arbitary 
% places on the page.
\usepackage[absolute,overlay%,showboxes
]{textpos}
% Set up the grid
%
% Note that [40mm,40mm] is the margin round the edge of the page --
% it is _not_ the grid size. That is always defined as 
% PAGE_WIDTH/HGRID and PAGE_HEIGHT/VGRID. In this case we use
% 15 x 25. This gives us a wide central column for text (7 grid
% spacings) and two narrow columns (3 each) at each side for 
% pictures, separated by 1 grid spacing.
%
% Note however that texblocks can be positioned fractionally as well,
% so really any convenient grid size can be used.
%
\TPGrid[40mm,40mm]{15}{25}  % 3 - 1 - 7 - 1 - 3 Columns

% Mess with these as you like
\parindent=0pt
%\parindent=1cm
\parskip=0.5\baselineskip

\begin{document}
\begin{frame}

%a first block for the title
\begin{textblock}{15}(0,0.8)

{\setlength{\baselineskip}{2.75\baselineskip}\hspace*{0.3\paperwidth}\Title{
Ion pairing controls rheological properties of ``processionary'' polyelectrolyte hydrogels
}\hfill \textit{Soft Matter} 2016, \textbf{12}, 9749-9758\par}

\centering

\vspace{0.5cm}
\LHead{Hassan Srour,\textit{$^{1}$} Martien Duvall Deffo Ayagou,\textit{$^{1}$} Thi Thanh-Tam Nguyen,\textit{$^{1}$}, Nicolas Taberlet,\textit{$^{2}$} S\'{e}bastien Manneville,\textit{$^{2}$}\\ Chantal Andraud,\textit{$^{1}$} Cyrille Monnereau,$^{\ast}$\textit{$^{1}$} and Mathieu Leocmach$^{\ast}$\textit{$^{3}$
}}\hspace{0.1\paperwidth}\texttt{\color{Main}\Large mathieu.leocmach@univ-lyon1.fr}\\

\affiliation{$^{1}$ Univ Lyon, Ens de Lyon, Universit\'e Claude Bernard Lyon 1, CNRS,
Laboratoire de Chimie, F-69342 Lyon, France.\\
$^{2}$ Univ Lyon, Ens de Lyon, Universit\'e Claude Bernard Lyon 1, CNRS,
Laboratoire de Physique, F-69342 Lyon, France.\\
$^{3}$ Univ Lyon, Universit\'e Claude Bernard Lyon 1, CNRS, Institut Lumi\`ere Mati\`ere, F-69622, VILLEURBANNE}
\end{textblock}%title

%example of an other block
\begin{textblock}{4}(0,4)
	\Head{Cation terminated polyanion}
	\tikzsetnextfilename{polymerisation}%
	blalah
\end{textblock} %synthesis

\end{frame}
\end{document}
```

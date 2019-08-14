# LaTeX frontmatter templates

This is a collection of my (Patrick Breheny) personal LaTeX templates.  People occasionally ask me to share them, so I've made them public.  Feel free to use these as is, or to use them a starting point for your own templates and tinker with them however you like.

In particular, `commands.tex` defines a ton of shortcuts that you may not like (among other things, they are specific to conventions in statistics); feel free to remove any of the commands you don't like, or replace them with your own commands, but be aware that other files in this package do load the `commands.tex` file, so it needs to exist.

## Installation

To use these files, you just need to put them somewhere in LaTeX's search paths.  If you're on a linux machine, I recommend putting them in the folder `~/texmf/tex/latex` (create this folder if it doesn't exist already).  If you're on a Mac, I believe the corresponding location is `~/Library/texmf/tex/latex`.  If you're on a Windows system, you'll have to Google it; I'm not sure where it is.

In other words, once installed, you should have a folder called `~/texmf/tex/latex/pb-latex` on your system.  Feel free to rename the folder to something other than `pb-latex`.

## Contents

The package provides frontmatter for three main types of documents:

* `breheny-article`: For articles...specifically scientific articles, but can also be used for other kinds of basic documents.
* `breheny-notes`: For beamer slides.
* `breheny-poster`: For posters.

There is also a `breheny-quiz` (something I use for quizzes); it's basically a wrapper to `breheny-article` but with some modifications.

The other files are helper files than can be used in any kind of output (article/slides/poster):

* `breheny-algorithm`: For typesetting algorithms.
* `breheny-code`: For typesetting code.
* `commands`: A bunch of macro shortcuts, such as `\x` for `\mathbf{x}`.
* `mar-1` and `mar-compact`: These set the margins for `breheny-article` to either 1 inch all around or the smallest margins I consider reasonable.  See below for example usage.

## Articles

Here is a minimal working example:

```
\documentclass[11pt]{article}
\input{breheny-article}
\input{mar-1}

% Include additional packages / define additional commands here

\title{My title}
\author{My name\\Department of Something\\University of Somewhere}
\date{\today}

\begin{document}

\maketitle

\abstract{My abstract}

Text goes here.

\end{document}
```

## Notes

Here is a minimal working example:

```
\documentclass{beamer}
\input{breheny-notes}
\author{My name}
\affiliation{University of Somewhere}
\title[My course]{My lecture topic}
\date{August 21}

\begin{document}

\begin{frame}
  \titlepage
\end{frame}

\section{My section}

\begin{frame}
\frametitle{Introduction}
\begin{itemize}
  \item <1-> Interesting point number 1
  \item <2-> Interesting point number 2
  \item <3-> Interesting point number 3
\end{itemize}
\end{frame}

\end{document}
```

## Poster

Still need to document this.

## Code

Still need to document this.

## Algorithm

Still need to document this.


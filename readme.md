# LaTeX frontmatter templates

This is a collection of my personal LaTeX templates. People occasionally ask me to share them, so I've made them public. Feel free to use these as is, or to use them a starting point for your own templates and tinker with them however you like.

In particular, `commands.tex` defines a ton of shortcuts that you may not like (among other things, they are specific to conventions in statistics); feel free to remove any of the commands you don't like, or replace them with your own commands, but be aware that other files in this package do load the `commands.tex` file, so it needs to exist.

## Installation

LaTeX looks for `.tex` files in a set of standard directories. By putting these templates in one of those paths, you can use them in any project without copying them into each folder.

On Linux and macOS, the recommended location is your personal TeX tree:

* **Linux:** `~/texmf/tex/latex`
* **Mac:** `~/Library/texmf/tex/latex`

You may need to create these folders if they don’t exist.

### Quick install (Linux/macOS)

Open a terminal and run:

```bash
mkdir -p ~/texmf/tex/latex
cd ~/texmf/tex/latex
git clone git@github.com:/pbreheny/pb-latex.git
```

After this, the files will live in:

```
~/texmf/tex/latex/pb-latex/
```

If you're on a Mac:

```bash
mkdir -p ~/Library/texmf/tex/latex
cd ~/Library/texmf/tex/latex
git clone git@github.com:/pbreheny/pb-latex.git
```

You can rename the folder (`pb-latex`) to anything you like.

Alternatively, you can manually download the `.zip` file (click the green button above), unzip, and drag the folder to the correct destination.

### Windows

On Windows, LaTeX also has a personal TeX tree, but the path depends on your TeX distribution. You'll have to search online for something like "TeX Live where is texmf?"

### Verifying it works

To test, run:

```bash
kpsewhich breheny-notes.tex
```

If LaTeX finds it and prints a path, it’s installed correctly.

## Contents

The package provides frontmatter for two types of documents:

* `breheny-article`: For articles...specifically scientific articles, but can also be used for other kinds of basic documents.
* `breheny-notes`: For beamer slides.

The other files are helper files than can be used in either kind of output (article/slides):

* `breheny-algorithm`: For typesetting algorithms.
* `breheny-code`: For typesetting code.
* `commands`: A bunch of macro shortcuts, such as `\x` for `\mathbf{x}`.
* `mar-1` and `mar-compact`: These set the margins for `breheny-article` to either 1 inch all around or the smallest margins I consider reasonable.

## Examples

Two kinds of examples are provided; both the source code and the resulting `.pdf` are included so that you can see what the output looks like.

* `examples/latex`: These are written in LaTeX and use the frontmatter directly through the use of `\input{}`.
* `examples/pandoc`: These are written in markdown and use the frontmatter via Pandoc templates. The templates themselves are in `examples/pandoc/templates`. These examples are written in [Quarto](https://quarto.org/), but the process of providing a template is the same for any Pandoc-based workflow (Rmarkdown, pure Pandoc markdown, etc.).


# LaTeX templates

This repository contains a collection of my personal LaTeX templates for articles and slides. People occasionally ask me to share them, so I've made them public. Feel free to use these templates as-is, or use them as a starting point for your own work.

These templates can be used directly from LaTeX or integrated into Quarto/Pandoc. Examples of both workflows are included in the `examples` folder.

In particular, `commands.tex` defines a ton of shortcuts that you may or may not like (among other things, they are specific to conventions in statistics); feel free to remove any of the commands you don't like, or replace them with your own commands, but be aware that other files in this package do load the `commands.tex` file, so it needs to exist.

## Organization

* `bin`: This includes a script called `singletex` that is useful for taking a LaTeX project in which the `.tex` code is split across multiple files and unifying it into a single `.tex` file for the sake of portability. This is very useful when submitting to arXiV or journals.
* `tex`: Files to include in LaTeX preamble
* `templates`: If you use Quarto or Pandoc, these set up the preamble for you.
* `examples`: Reproducible examples using these templates and frontmatter
  * `examples/latex`: These use LaTeX directly
  * `examples/quarto`: These use LaTeX indirectly, through Quarto

## Installation

### Simple approach

Just copy any file you need into your project directory.

This is obviously easy, although you end up with multiple copies of the same files. A better approach in the long run is to place the `tex/` directory somewhere on your LaTeX search path; see the next section for details.

### Advanced approach

LaTeX looks for `.tex` files in a set of standard directories. By putting these templates in one of those paths, you can use them in any project without copying them into each folder.

On Linux and macOS, the recommended location is your personal TeX tree (you can change the location if you set your `TEXINPUTS` environment variable):

* **Linux:** `~/texmf/tex/latex`
* **Mac:** `~/Library/texmf/tex/latex`

You may need to create these folders if they don’t exist.

A quick Linux install script is:

``` bash
mkdir -p ~/texmf/tex/latex
cd ~/texmf/tex/latex
git clone git@github.com:/pbreheny/pb-latex.git
```

If you're on a Mac:

``` bash
mkdir -p ~/Library/texmf/tex/latex
cd ~/Library/texmf/tex/latex
git clone git@github.com:/pbreheny/pb-latex.git
```

On Windows, the path depends on your TeX distribution. You'll have to search online for instructions relevant to your distribution.

### Test

To test whether you've installed it correctly, run:

```bash
kpsewhich breheny-notes.tex
```

If LaTeX finds it and prints a path, it’s installed correctly.

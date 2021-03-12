# TemplateCheatsheet

A template to create a cheat sheet (LaTeX).

## Dependencies

* [python v3.9](https://www.python.org/)
* [pygments v2.7.2 ](https://github.com/pygments/pygments)
* [minted v2.5](https://github.com/gpoore/minted)
* [listings v1.8](https://www.ctan.org/pkg/listings)
* [tabularx v2.11](https://www.ctan.org/pkg/tabularx)


## Usage

You need to install pygments with pip3 (python) to use the package minted.

```shell
$ pip3 install pygments
```

Verify if pygmentize is installed and in your PATH environment with:

```shell
$ pygmentize -V
```

> If the installation is correct, you will see a message like this: `Pygments version 2.7.2, (c) 2006-2020 by Georg Brandl.`. Otherwise you will need to reboot or to add the ```python\script``` directory in your PATH.

To generate the pdf, you will need to add `-shell-escape` like this:

```bash
$ pdflatex.exe your_file.tex -shell-escape
```

To use the template, you just need to add this line after the documentclass definition:

```
\usepackage{cheatsheet}
```

> Note: The package mutlicols and tcolortab seems to have a problem to determine the height of the file. This may be corrected in newer versions. 
> But for now, you will need to pay attention to the arrangement of your blocks. To balance this issue, I've added two manual breaks for the Note and Important block.

## Theme

You can set a light and dark theme in the package, for this you just need to (un)comment the line `\def\darktheme{}`.

![Dark theme](https://github.com/Atlanta53/TemplateCheatSheet/blob/main/res/darkTheme.PNG)
![Light theme](https://github.com/Atlanta53/TemplateCheatSheet/blob/main/res/lightTheme.PNG)

## Blocks

I implemented 4 types of blocks:

### Text

You can select between two type of texts :

```
\begin{Text}{Title}
    ...
\end{Text}
```

```
\begin{TextColor}{Title}{Color}
    ...
\end{TextColor}
```

### Note

To separate a Note block, you can call `\splitNote`. This will break the Note block and start a new one.

```
\begin{Note}{Title}
    ...
\end{Note}
```

### Important

To separate a Important block, you can call `\splitImportant`. This will break the Important block and start a new one.

```
\begin{Important}{Title}
    ...
\end{Important}
```

### Code

#### Minted

> The language implemented are cpp, python, bash, js, PHP.

```
\begin{CodeMinted}{Language}
    ...
\end{CodeMinted}

or

\codeMinted{Language}{ ... }
```

#### Listings

```
\begin{CodeListings}{Language}
    ...
\end{CodeListings}

or

\codeListings{Language}{ ... }
```

### Table

```
\begin{Table}{Title}{Arrangment}
    ...
    . & . & . \hline
    ...
\end{Table}
```

## Image and List

### Image

```
\image{Path}{Title}
```

### List

```
\begin{List}{Color}
    ...
    \item
    ...
\end{List}
```

## License

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
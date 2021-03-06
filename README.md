This is the LaTeX source for the textbook **Methods of Algebra** (in Chinese: 代数学方法), volume 1.

The book has been published by Higher Education Press (Beijing), ISBN 978-7-04-050725-6. The PDF version and the errata are available on the author's web page. The contents in this book are somewhat "fronzen", and the spotted mistakes will be corrected in the next edition.

It is hoped that these files will be of some help to those professors, students as well as amateurs who wish to write serious Chinese books in Mathematics or Physics without too much TeXnical trouble.

# How to compile

## System requirements
The files are to be compiled using XeLaTeX with the xeCJK package. The reader is assumed to work under the UN*X + bash environment.

The recipes below can be tweaked to work under Windows, but this is not recommended. The simplest solution is to go open-source.

We only need the standard packages and fonts, such as
- [TeX Live](https://tug.org/texlive), including the programs latexmk, xindy and biber.
- Standard fonts included in TeX Live.
- The [Noto Sans CJK](https://github.com/googlei18n/noto-cjk) fonts, which should be installed system-wide.

Make sure that all the relevant packages/programs are installed. For reference, the author made the compilation under Linux, using TeX Live 2018 with most packages installed.

## Clone the files
As a preparation for the compilation process, we will clone the files into `~/AlJabr-1` in our home directory. In command line, type
```
cd ~
git clone https://github.com/wenweili/AlJabr-1
```

## Compile the TeX source

Move to the directory
```
cd ~/AlJabr-1
```
Then, either type
```
latexmk -pdf -pdflatex="xelatex -shell-escape -interaction=nonstopmode %O %S" Al-jabr-1
```
under bash, or more simply
```
make
```

Have a cup of coffee since this will take several minutes. The resulting PDF file should appear as **Al-jabr-1.pdf** in the same directory. Note that the main file is **Al-jabr-1.tex**.

To clean up everything in our directory except the PDF file, type
```
make clean
```

# The document class AJbook
The book is written in the **AJbook** class (AJbook.cls). This is a general-purpose document class, based on XeLaTeX/xeCJK and the standard book class in LaTeX, whose aim is to produce Chinese books in Mathematics/Physics of professional quality. Its basic usage is illustrated in Template-AJbook.tex; type
```
latexmk -pdf -pdflatex="xelatex -shell-escape -interaction=nonstopmode %O %S" Template-AJbook
```
or more simply
```
make template
```
to compile the template.

The fonts and other apppearances are customizable through several config files; please read the source files carefully for further details. The Template-AJbook.tex file follows the original configurations of the book.

# The errata
The errata is produced from **Errata-Al-jabr-1.tex**, which is based on the really simple document class file **AJerrata.cls**. To compile it, type
```
xelatex Errata-Al-jabr-1
```
or
```
make errata
```
in the same directory.

# Feedback
In case of problems of compilation, please kindly report to the author. Make sure that all the system requirements above are met, and provide detailed error messages. Other suggestions are also welcome.

# License
The entire codebase is under [CC BY 4.0](http://creativecommons.org/licenses/by/4.0/).

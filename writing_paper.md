---
mathjax: true
mermaid: true
---
# writing paper
T. Yamato @ NU

Dec. 05, 2023

## Introduction
Productive environment for writing paper is very important for every scientist. Nowadays, we usually work with many coworkers with different backgrounds from different locations. Therefore, we need to exchange our ideas/comments/opinions in an efficient manner. For instance, *GitHub* provides an ideal solution for this purpose. 

For writing papers, we usually use documentation tools such as MS-WORD, Latex, etc... Although your manuscript with either WORD or Latex format will be accepted by most scientific journals without any problem, it does not provide an ideal resource especially when you write a paper with your colleagues together. 

Markdown text is getting more and more popular especially among data scientists and computer programmers. Recently, there are so many useful Markdown editors, such as *Visual Studio code*, *Typora*, etc... available for us. Here I will show my recent effort to write scientific paper with *VS code* with using Citation Manager *Zotero* and share relevant materials via GitHub with your coworkers (see below). Note that you can visit clickable links indicated by red boxes below.

For japanese readers, the following links would be extremely helpful. 
- [exporting bibliography from zotero using pandoc (part I)](https://zenn.dev/sky_y/articles/pandoc-advent-2020-bib1)

- [exporting bibliography form zotero using pandoc (part II)](https://zenn.dev/sky_y/articles/pandoc-advent-2020-bib2)


```mermaid
graph TB
subgraph YOUR PC

subgraph BROWSER
A[chrome]-.-B[zotero connector]
click B "https://www.zotero.org/support/connector"
end

subgraph CITATION MANAGER
C[zotero]-.-D[better bibtex]
click C "https://www.zotero.org"
click D "https://retorque.re/zotero-better-bibtex/"
D-->E[my_library.bib]
I[<journal>.csl]
end

subgraph Markdown editor
F[VS code]-.-G[citation picker for zotero]
click F "https://code.visualstudio.com"
click G "https://marketplace.visualstudio.com/items?itemName=mblode.zotero"
G-->H[paper.md]
end

subgraph Document formatter
J[pandoc]-->BB[paper.pdf]
end

subgraph Bibtex manipuration tool
AA[bibtool]
click AA "http://www.gerd-neugebauer.de/software/TeX/BibTool/en/"
end

subgraph Graphic tool
P[Figures]
end

subgraph Perl
AAA[mdbibexport.pl]
click AAA "https://github.com/robert-winkler/mdbibexport"
end

E-->AA
H-->AA
AA-->AAA
AAA-->N[paper.bib]
B-->|"add references"|C
E-->G

H-->J
I-->J
P-->J
N-->J

subgraph Paper materials
A3[material package]
end

H-->A3
I-->A3
P-->A3
N-->A3
BB-->A3

end

subgraph GitHub
A1[Your repository]
end

subgraph Coworkers
A2[coworker]
end

A3---A1
A1-->A2
A2-->A1

style B stroke: red
style C stroke: red
style D stroke: red
style F stroke: red
style G stroke: red
style AA stroke: red
style AAA stroke: red
style H fill:orange
style N fill:orange
style P fill:orange
```
## Citation manager and Browser
I was using *Mendeley* before migrating to *Zotero*, the latter of which seems to be more useful for us. By using *Better Bibtex* extention with *Zotero*, you can automatically keep updating your `.bib` file that contains your personal reference library. When you use, for instance, *Google chrome* for finding a scientific paper you wish to add to your library, you can easily cite the reference in your manuscript by using *Zotero connector* extension for *Google chrome*. 

### Zotero
For (japanese) readers, the following link would be helpful for installing Zotero and Zotero connector: [tips for Zotero installation](https://guides.lib.fsu.edu/zotero/install/connector) ([japanese tips for Zotero installation](https://www.noguchilabo.com/zotero/#toc6)). Note that MS-WORD plugin, which allows you CWYW, can be installed as well by downloading Zotero software. 


## Editing markdown text
*VS code* is one of the most popular markdown editors, today. By using *Citation picker for Zotero* extension, you can select a reference from your Zotero library and cite the reference at any position in your paper. Usually, your original reference library, `my_library.bib`, kept by *Zotero* contains huge amount of references. Therefore, it is not suitable to be shared with your coworkers. By using `bibtool` and a perl script, `mdbibexport.pl`, you can extract the references that appear in your markdown file, `paper.md`, and save it as, for instance, `paper.bib`. These two files constitute the essential part of your paper. Also, you will need specify a suitable citation style, which is described in a file with `.csl` extension. For instance, *Nature* citation style is described in `nature.csl`. Finally, you can generate a PDF file, `paper.pdf` from `paper.md`, `paper.bib`, and `<journal>.csl` files, using *Pandoc* document formatter. Of course, you may wish to include links to original figures in the markdown text. You can use, for instance, *draw.io* to create an *svg* file for your paper. A care must be taken however, in such cases. For example, an *svg* figure containing text may not be converted to PDF file by *Pandoc*. Anyway, you can push your paper materials including `paper.md`, `paper.bib`,`<journal>.csl`, and original figure files, to your github repository so that you can share these materials with your coworkers. Of course, you can include the pdf file of your paper as well.

## YAML headers in paper.md
Before writing a paper using markdown file, a [YAML header](https://zsmith27.github.io/rmarkdown_crash-course/lesson-4-yaml-headers.html) is quite useful for defining the format of the paper. Here is an example of YAML header for writing a journal article:

```

---
title: Local Thermal Transport in an $\alpha$-helical Protein
header-includes: # define some settings for math equations
    - \usepackage{bm}
    - \usepackage{textalpha} 
    - \usepackage[left]{lineno}
    - \linenumbers
    - \usepackage{setspace}
    - \doublespacing
bibliography:  # the reference library
    - "paper/bibliography_yamato.bib"
    - "paper/bibliography_ttwang.bib"

csl: "paper/american-chemical-society.csl" # citation style
link-citations: True
urlcolor: blue
refcolor: blue

#fontfamily: libertineotf
output: # output setting for pdf and docx format
    word_document:
      reference_docx: "template.docx"
      pandoc_args:
      - --lua-filter=scholarly-metadata.lua
      - --lua-filter=author-info-blocks.lua
    pdf_document:
      latex_engine: xelatex
      keep_tex: true
      pandoc_args:
      - --lua-filter=scholarly-metadata.lua
      - --lua-filter=author-info-blocks.lua
mainfont: Times New Roman # font style
sansfont: Linux Biolinum O
fontsize: 12pt 
spacing: double
zotero: # reference citation library
  library: <group name> # omitted to use your personal library
  scannable-cite: false # only relevant when you're compiling to scannable-cite .odt
  client: <zotero or jurism> # defaults to zotero
  author-in-text: false # when true, enabled fake author-name-only cites by replacing it with the text of the last names of the authors
  csl-style: apa # pre-fill the style
---

```

### VS code citation picker for Zotero
Mac (Linux/Windows) users can select *citation picker for zotero* by "Command+Shift+P" (Ctrl+Shift+P) while editing your markdown text using VS code. Then you can insert any reference at any position in your text from the reference library maintained in your Zotero environment. The following is an example of markdown text. Two references @Yamato2009 and @yamatoNormalModeAnalysis2019 are cited in the text, and the list of references will be inserted in `References Bibliography` section by using *Pandoc*. 

"test.md"
```
# test
  
this is a pen @Yamato2009.

![Figure 1](img/1Dwell-2.svg)

this is another pen @yamatoNormalModeAnalysis2019.

## References Bibliography

```

### Better bibtex for Zotero
You can install *better bibtex add-on following the link below:
[tips for installing *better bibtex for zetero*](https://library.unimelb.edu.au/recite/reference-management-software/latex-and-bibtex/zotero).

### bibtool and mdbibexport.pl
Mac users can install *bib-tool* using *homebrew*.

```
brew install bib-tool (return)
```
Also, source code is available at the *bib-tool* [website](http://www.gerd-neugebauer.de/software/TeX/BibTool/en/). 

I happen to find an useful perl script *mdbibexport.pl*. Suppose that your personal reference library, "my_library.bib" is maintained by *Zotero*, and your markdown text file is "test.md". Then you can extract the bibliography information of the two references @Yamato2009 and @yamatoNormalModeAnalysis2019 from "my_library.bib" by using *mdbibexport.pl*. To do so, you just enter `perl mdbibexport.pl`. Then you will be asked the necessary file names. As a result, you get the following [mdbibexport.bib](mdbibexport.bib) file in your directory.

### pandoc-crossref
When we are writing a paper or thesis, it is inevitable that there are many equations, figures and tables. For an efficient way to manage them without numbering mistakes,  automatically numbering them through the whole text is quite necessary. To this end, we recommend you to use *pandoc-crossref*. The *pandoc-crossref*  is a pandoc filter for numbering figures, equations, tables and cross-references to them. You can find the [pandoc markdown](https://pandoc.org/MANUAL.html#pandocs-markdown) usage here. 

### pandoc
Now you have everything you need to generate a PDF file for your markdown text using *Pandoc*. 

```
pandoc -s -o\
	paper/paper.pdf \
	paper/paper.md \
	--filter pandoc-crossref \
	--citeproc --bibliography=mdbibexport.bib\
	--to=latex

```

Here's a list of relevant files.
- [nature.csl](nature.csl)
- [test.pdf](test.pdf)
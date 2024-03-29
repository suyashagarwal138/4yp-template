# DPhil / PhD doctoral thesis LaTeX class


This repository contains a LaTeX class (OxEngThesis) to write formal academic documents for a student of the [Department of Engineering Science](https://www.eng.ox.ac.uk) at the [University of Oxford](https://www.ox.ac.uk). For example, my undergraduate students have used this class to write 4<sup>th</sup>-year project (4YP) reports. My doctoral students have typically used this class to write their 1<sup>st</sup>-year Transfer of Status report, 2<sup>nd</sup>-year Confirmation of Status report and their final DPhil thesis. The typical 4YP report contains around 50 pages, whereas a doctoral thesis is a much larger document.

Although I originally created this class for a student at Oxford, I also included in this repository some examples for a PhD thesis for the Massachusetts Institute of Technology and (cough, cough) the University of Cambridge. It should be easy for you to adjust this class to suit the requirements of your academic institution.

LaTex itself is very portable. However, I developed this class under Linux and macOS environments using the latest LaTeX distributions. I have not tested compiling a LaTeX document in Microsoft Windows, but some of my students reported that it works. If you find any problems for Windows, please report any issues to me. Event better, I encourage you to contribute your fixes.

&nbsp;

> "OxEngThesis" is free software: you can redistribute it or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, version 2 only. Check the file [COPYING](COPYING) for more information on the license and copyright.

&nbsp;

As a research student, a proportion of your time will be devoted to writing science in a formal academic style. There are many resources that will help you to write your thesis, such as [Writing your thesis](https://www.mpls.ox.ac.uk/training/resources-for-researcher-and-career-development/completing-your-dphil/writing-up-your-thesis), [Completing your doctorate](https://www.vitae.ac.uk/doing-research/doing-a-doctorate/completing-your-doctorate), [Essay and dissertation writing skills](https://www.ox.ac.uk/students/academic/guidance/skills/essay) and also other [resources for new students](https://cameralab.eng.ox.ac.uk/resources_new_students.html). Steven Pinker's talk on [Linguistics, Style and Writing in the 21st Century](https://youtu.be/OV5J6BfToSw) will provide you with sound advice on writing (hopefully you will put the passive voice to rest after watching the video). 

My students have found very helpful to use the LaTeX typesetting system to write reports, theses, journal papers or other academic documents. You can write your LaTeX documents from scratch, however, it is often easier to start with an already written class template. This way you can focus on (as your supervisor expects) writing about your exciting research contributions, rather than spending time formatting your document or applying other cosmetic changes that just waste everybody's time and distract the reader. 

The OxEngThesis class is based on the [memoir](https://ctan.org/pkg/memoir) package, with the addition of several other packages and extra features useful to format a typical academic document. The main class file is [oxengthesis.cls](oxengthesis.cls). One sample source file is provided: [sample_dphil_thesis.tex](sample_dphil_thesis.tex) to get you started writing your thesis. You can check the [sample_dphil_thesis-sample_output.pdf](sample_dphil_thesis-sample_output.pdf) file to view an example of the output PDF document for a doctoral thesis.

This tutorial summarises some of the features available in the OxEngThesis class. Take a look at the [oxengthesis.cls](oxengthesis.cls) file and the [sample_dphil_thesis.tex](sample_dphil_thesis.tex) source file for a more complete overview. Additionally, this tutorial is replicated as "Chapter 0: The OxEngThesis LaTeX class" in the [sample_dphil_thesis-sample_output.pdf](sample_dphil_thesis-sample_output.pdf), so you can view examples of the LaTeX syntax to write your document.

&nbsp;


## Requirements


There are several options for writing in LaTeX, including online versions such as Overleaf. I don't recommend online editors, as you will be writing long documents with several figures, tables and other elements. In my experience, having LaTeX installed locally in your computer is a better option.

You will need a modern LaTeX compiler installed in your system, at minimum version 2017. Most modern operating systems use [TexLive](https://www.tug.org/texlive/) as the preferred LaTeX typesetting system. If you are using Linux, TexLive is already pre-installed or is readily available from your distribution's software repository, for example: [LaTeX in Fedora](https://docs.fedoraproject.org/en-US/neurofedora/latex/) and [LaTeX in Ubuntu](https://help.ubuntu.com/community/LaTeX). For macOS, you can download and install the latest [MacTeX](https://tug.org/mactex) distribution. For Microsoft Windows, follow the installation instructions described in [TexLive on Windows](https://tug.org/texlive/windows.html).

Install the Carlito font (if it's not already installed in your system). Follow the instructions for your particular operating system in the [fonts](fonts) directory, for example for [Linux](fonts/INSTALL_FONTS_LINUX.md) or [macOS](fonts/INSTALL_FONTS_macOS.md). If you are using Microsoft Windows, also install the Latin Modern Math font.


## LaTeX editors


There are several editors available that will make your life easier when writing LaTeX documents and, ultimately, generating the final PDF file (a.k.a compiling the LaTeX source files). For macOS, [Texifier](https://www.texifier.com) works really well. Good editors for Linux are [Kile](https://apps.kde.org/en-gb/kile) and [TeXMaker](https://www.xm1math.net/texmaker). If you know what software is good for Microsoft Windows, let me know so I can add it to my recommendation list.

The LaTeX files in this repository require the [LuaLaTeX](https://en.wikipedia.org/wiki/LuaTeX) engine. You editor should allow you to configure LuaLaTeX as the typesetting engine for your document and automatically take care of the compilation process to generate the final PDF document.

&nbsp;


# Writing your thesis


This tutorial is replicated as "Chapter 0: The OxEngThesis LaTeX class" in the [sample_dphil_thesis-sample_output.pdf](sample_dphil_thesis-sample_output.pdf), so you can review examples on how to write your LaTeX document.


## Preparing your document


After you installed your preferred LaTeX editor, make a copy of the [sample_dphil_thesis.tex](sample_dphil_thesis.tex) sample file provided in this repository. Throughout this tutorial, I will call this new file your "*main LaTeX source file*". The minimum content you need is:


```latex
\documentclass{oxengthesis}

\title       {The title of your thesis}
\author      {Your name}
\college     {The name of your college}
\supervisor  {The name(s) of your supervisor(s)}
\date        {The academic term of submission}
```


From your "*main LaTeX source file*", remove the line that includes the OxEngThesis class documentation. It is a line similar to:


```latex
\include{oxengthesis_class_documentation}
```


&nbsp;

>**NOTE**: The line above includes the LaTeX version of this README file. It shows how you can use the features provided by the OxEngThesis class in your document. It is numbered as "Chapter 0" in the sample PDF file [sample_dphil_thesis-sample_output.pdf](sample_dphil_thesis-sample_output.pdf) so not to change the flow of the rest of the document.

&nbsp;


The *frontmatter* of the thesis will be automatically created depending on the type of document you are writing, either a doctoral thesis or a project report. If you want more control, you can review how the '\makefrontmatterpages' command is defined in the [oxengthesis.cls](oxengthesis.cls) class file. If you want all the sections in the *frontmatter* to appear, you will need to create the following files:

- **[abstract.tex](abstract.tex)** : If you want the "Abstract" page
- **[dedication.tex](dedication.tex)** : If you want the "Dedication" page
- **[declaration.tex](declaration.tex)** : If you want the "Declaration" page
- **[acknowledgements.tex](acknowledgements.tex)** : If you want the "Acknowledgements" page
- **[publications.tex](publications.tex)** : If you want the "List of publications" page
- **[glossary.tex](glossary.tex)** : If you want the "List of abbreviations" page

If any of the files above are missing, that particular page won't be created in the *frontmatter*. This is useful if you are just preparing a draft version of your thesis for your supervisor to correct. 

Similarly for the *backmatter* part of your thesis, add all the BibTeX citations to a file named [references.bib](references.bib) if you want the "Bibliography" section to be created at the end of your document. 


## Writing a "Transfer of Status" or "Confirmation of Status" report


There are two [Key milestones](https://www.ox.ac.uk/students/academic/guidance/graduate/research/status/DPhil) for which DPhil students are expected to submit substantial piece of written research work, or reports. They are the "[Transfer of Status](https://www.mpls.ox.ac.uk/graduate-school/information-and-resources-for-supervisors/transfer-of-status)" at the end of your first year, and the "[Confirmation of Status](https://www.mpls.ox.ac.uk/graduate-school/information-and-resources-for-supervisors/confirmation-of-status)" at the end of your second year. 

For these milestones, you will often be required to submit a report with all the details of your research contributions. This document is often around 50-60 pages in length and does not need all the sections that a doctoral thesis has (i.e. declaration, dedication or list of publications). 

You can write a *Transfer of Status* report by simply providing the "*report*" option when you load the OxEngThesis class, and defining the "*degree*" variable as shown in the following code snippet:


```latex
\documentclass[report]{oxengthesis}

\title       {The title of your report}
\author      {Your name}
\degree      {{\huge Transfer of Status Report}}
\college     {The name of your college}
\supervisor  {The name(s) of your supervisor(s)}
\date        {The academic term of submission}
```


You can write a *Confirmation of Status* report by simply providing the "*report*" option when you load the OxEngThesis class, and defining the "*degree*" variable as shown in the following code snippet:


```latex
\documentclass[report]{oxengthesis}

\title       {The title of your report}
\author      {Your name}
\degree      {{\huge Confirmation of Status Report}}
\college     {The name of your college}
\supervisor  {The name(s) of your supervisor(s)}
\date        {The academic term of submission}
```


Note that the "*report*" package option is just a shortcut to not include the dedication, declaration and publications pages and format the title page accordingly.


## Writing a 4<sup>th</sup>-Year Project (4YP) report


If you are an undergraduate student at the University of Oxford reading [Engineering Science](https://eng.ox.ac.uk/study/undergraduate/your-degree), you will carry out a self-led project during your fourth year. It usually involves original research or significant design and construction work, undertaken in close consultation with an academic supervisor. At the end of your project (usually by the beginning of Trinity term), you will need to submit a report with all the details of your research contributions. This document is often around 50 pages in length and does not need all the sections that a doctoral thesis has (i.e. declaration, dedication or list of publications). 

You can write a 4YP report by simply providing the "*report*" option when you load the OxEngThesis class, and defining the "*degree*" variable as shown in the following code snippet:


```latex
\documentclass[report]{oxengthesis}

\title       {The title of your report}
\author      {Your name}
\degree      { {\huge 4$^{th}$-Year Project Report} }
\college     {The name of your college}
\supervisor  {The name(s) of your supervisor(s)}
\date        {The academic term of submission}
```


## Creating the PDF output


The source files in this repository require the [LuaLaTeX](https://en.wikipedia.org/wiki/LuaTeX) engine. You editor should allow you to configure LuaLaTeX as the typesetting engine for your document and automatically take care of the compilation process to generate the final PDF document from your "*main LaTeX source file*".

If you want to compile your "*main LaTeX source file*" from the command line, you can use the script [compile_document.sh](compile_document.sh) provided in this repository. This script only works in a Linux or macOS system. For example, to compile the sample thesis provided, you will execute the following command in the terminal:


```shell
$ ./compile_document.sh  sample_dphil_thesis.tex
```


If you want to delete all the temp or auxiliary files LaTeX created during the compilation process, you can run:


```shell
$ ./remove_latex_aux_files.sh
```


If you are compiling the document manually, you would need to run the [latexmk](https://ctan.org/pkg/latexmk) build command (already part of your LaTeX distribution) in the following order:


```shell
$ latexmk -pdflatex=lualatex -pdf  sample_dphil_thesis.tex
$ makeglossaries sample_dphil_thesis.tex
$ latexmk -pdflatex=lualatex -pdf  sample_dphil_thesis.tex
```


## Customising the title page


Although I originally wrote this LaTeX template for a student at the University of Oxford, it should be easy for you to customise it to suit the requirements of your academic institution. The [default title page](titlepage-oxford.tex) is simple and customisable. The class template defines some variables you can use. At minimum, you need to provide the following definitions in the preamble of your "*main LaTeX source file*":

- **\title{}**:      The main title of the thesis/report
- **\author{}**:     The author of the thesis/report

You can define the following optional variables:

- **\supervisor{}**: The name of your thesis supervisor. The default value is: "*SUPERVISOR NAME*"
- **\college{}**: Your college affiliation, if you are an Oxford student. The default value is: "" (an *empty string*)
- **\degreeprefix{}**: Text printed before the degree name. The default value is: "*A thesis submitted for the degree of*"
- **\degree{}**: The name of the degree. The default value is: "*Doctor of Philosophy*"
- **\department{}**: Your university department. The default value is: "*Department of Engineering Science*"
- **\university{}**:   The name of your university. The default value is: "*University of Oxford*"
- **\universitylogo{}**: File name of the university's logo, without the file extension. The default value is: "*oxford-logo*" (which will load the image file [oxford-logo.png](figures/oxford-logo.png))
- **\date{}**: The date of publication of the thesis, such as "*Hilary Term, 2048*". If you leave it blank, it will print the current date (useful when sending a draft to your supervisor)


The title pages for a DPhil/PhD thesis and for a 4YP report can be created with very similar code. They both use the default title page "[titlepage-oxford.tex](titlepage-oxford.tex)". The only difference is the use of the ``\verb|report|'' package option. For example, the title page for the DPhil thesis can be created with the following code:


```latex
\documentclass{oxengthesis}

\title{The long-term effects of climate change on farming in Middle Earth}
\author    {Samwise Gamgee}
\college   {Jesus College}
\supervisor{Professor J.R.R. Tolkien}
\date      {Hilary Term, 2048}
```


The title page for the 4YP report can be created with the following code:


```latex
\documentclass[report]{oxengthesis}

\title{The long-term effects of climate change on farming in Middle Earth}
\author    {Samwise Gamgee}
\degree    { {\huge 4$^{th}$-Year Project Report} }
\college   {Jesus College}
\supervisor{Professor J.R.R. Tolkien}
\date      {Hilary Term, 2048}
```

The code above produces the following outputs:

&nbsp;

<p align="center">
    <kbd><img src="./figures/dphil-title_page.png" alt="Title page" width="250" border=1 /></kbd>
    <kbd><img src="./figures/4yp-title_page.png" alt="TOC page 1" width="250" border=1 /></kbd>
</p>

&nbsp;


## Create your own title page


If you don't provide a custom title page, the [oxengthesis.cls](oxengthesis.cls) class template will load the default title file [titlepage-oxford.tex](titlepage-oxford.tex) shown above. If the layout of the default title page does not fulfil your or your university's requirements, you can create your own title page. To do so, you will need to follow the 3 steps described below. As an example, we will create a custom title page for a PhD thesis for a student at the Massachusetts Institute of Technology:

1. Create a new LaTeX source file and add your own definitions, such as the example file [titlepage-mit.tex](titlepage-mit.tex)

2. Define the "**\titlepage{}**" variable in the preamble of your "*main LaTeX source file*". For example, after the "\author{}" variable as in:


```latex
\title    {Protein expression of the X-factor mutator gene in Homo Sapiens}
\author   {Charles F. Xavier}
\titlepage{titlepage-mit.tex}
```


3. Recompile your "*main LaTeX source file*". An example of the output is:

&nbsp;

<p align="center">
    <kbd><img src="./figures/mit_phd-title_page.png" alt="Title page" width="350" border=1 /></kbd>
</p>

&nbsp;

The following text in the preamble of your "*main LaTeX source file*" will use the "[titlepage-cambridge.tex](titlepage-cambridge.tex)" file to create a title page for a student at the University of Cambridge:


```latex

\title      {Protein expression of the X-factor mutator gene in Homo Sapiens}
\author     {Charles F. Xavier}
\college    {Pembroke College}
\degreeprefix {A thesis submitted for the degree of}
\degree     {Doctor of Philosophy}
\supervisor {Professor Albus Dumbledore}
\department {Department of Engineering}
\university {University of Cambridge}
\universitylogo{cambridge-logo}
\date       {June 2048}
\titlepage  {titlepage-cambridge.tex}
```


The sample output is shown below:

&nbsp;

<p align="center">
    <kbd><img src="./figures/cambridge_phd-title_page.png" alt="Title page" width="350" border=1 /></kbd>
</p>

&nbsp;

The [oxengthesis.cls](oxengthesis.cls) class makes available new LaTeX commands that you can use in your new custom title document. These new commands are based on the variables defined in the preamble of your "*main LaTeX source file*":

- The **\title{}** variable in the preamble will map to the command **\TitleName**
- The **\author{}** variable in the preamble will map to the command **\AuthorName**
- The **\supervisor{}** variable in the preamble will map to the command **\SupervisorName**
- The **\college{}** variable in the preamble will map to the command **\CollegeName**
- The **\degreeprefix{}** variable in the preamble will map to the command **\DegreePrefix**
- The **\degree{}** variable in the preamble will map to the command **\DegreeName**
- The **\department{}** variable in the preamble will map to the command **\DepartmentName**
- The **\university{}** variable in the preamble will map to the command **\UniversityName**
- The **\universitylogo{}** variable in the preamble will map to the command **\UniversityLogo**
- The **\date{}** variable in the preamble will map to the command **\DegreeDate**

Check the files [titlepage-oxford.tex](titlepage-oxford.tex), [titlepage-mit.tex](titlepage-mit.tex) and [titlepage-cambridge.tex](titlepage-cambridge.tex) for examples on how to use the available commands in your new title page.

&nbsp;


# Package options


## Default package options


By default, the class is formatted to produce a doctoral thesis for the University of Oxford. If you don't provide any package options, such as:


```latex
\documentclass{oxengthesis}
```


the output document will be created with the following options


```latex
\documentclass[10pt,a4paper,openany,onecolumn,twoside,final,font=Carlito,mathfont="Latin Modern Math",headingcolour={0,0,0},leftmargin=4cm,rightmargin=2cm,topmargin=2cm,bottommargin=2.5cm]{oxengthesis}
```


which will produce a thesis using a 10-point Carlito font on A4 paper size. Page margins will be formatted as required by Oxford. Chapters will start on either recto or verso pages (openany). Note that the options "[onecolumn,twoside,final]" cannot be changed. 


The OxEngThesis class template is based on the [memoir](https://ctan.org/pkg/memoir) LaTeX package. As such, you can pass most of the memoir's option and, therefore, customise your document even further.


## Page size and margins


By default, the page size and margins are set to comply with the requirements of the University of Oxford. Other institutions have different requirements. For example, the requirements for a thesis at the Massachusetts Institute of Technology are ([taken from MIT libraries](https://libraries.mit.edu/distinctive-collections/thesis-specs)):


```
... For the main body of the text, including appendices and front matter, font size should be at least 11-point ...

... Top, bottom, and both side margins must be at least an inch wide (1″) to allow for binding and trimming....
```


Therefore, you would configure the class with the following options (Note that the left margin is larger):


```latex
\documentclass[11pt, letterpaper,leftmargin=1.5in,rightmargin=1in,topmargin=1in,bottommargin=1in]{oxengthesis}
```


## Fonts


By default, the main font is 10-point "[Carlito](https://ctan.org/tex-archive/fonts/carlito?lang=en)" and the font for equations and formulas is "[Latin Modern Math](https://ctan.org/tex-archive/fonts/lm-math?lang=en)". You can change to, for example, 11pt Arial as the main font and "tex-gyre-math-termes" as the font for equations with the following package options:


```latex
\documentclass[11pt,font=Arial,mathfont="TeX Gyre Termes Math"]{oxengthesis}
```


## Mini-table of contents for each chapter


If you have a recent version of LaTeX installed (TeXLive version 2022 works) in your system and would like to have a short table of contents at the beginning of each chapter, you can simply add the "*chaptertoc*" option to your document:


```latex
\documentclass[chaptertoc]{oxengthesis}
```


Below is a sample output for one chapter:

<p align="center">
    <kbd><img src="./figures/dphil-chap_minitoc.png" alt="Mini-table of contents for each chapter" width="350" border=1 /></kbd>
</p>


I use the [minitoc](https://ctan.org/pkg/memoir) LaTeX package to create the table of contents for each chapter. Previous versions of the minitoc class where incompatible with the [memoir](https://ctan.org/pkg/memoir) class. I tested TexLive 2022 and MacTeX 2022, they both work fine.


## Abstract page for the Examination Schools


When submitting your final thesis to the "Examination Schools" (located on High Street) at the University of Oxford to schedule your viva examination, you are typically required to submit two printed copies of your thesis (soft-bound). Additionally, you are required to provide two separate one-page printed copies of your abstract. The stand-alone abstract page should contain your name, college affiliation and is NOT meant to be part of the binding of your thesis. To create this single stand-alone page of your abstract, add the "*frontabstract*" option to your document, as in:


```latex
\documentclass[frontabstract]{oxengthesis}
```


The page will be created before the main title page. Below is a sample output:

<p align="center">
    <kbd><img src="./figures/dphil-front_abstract_page.png" alt="Abstract page for the Examination Schools" width="350" border=1 /></kbd>
</p>


## Review editing mode


Your thesis supervisor may request you to print your document with double line spacing so he/she can correct your draft (the red pen!). You can simply add the "*review*" option to your document:


```latex
\documentclass[review]{oxengthesis}
```


## Different colour for section headings


The default font colour for section and subsection headings is black. You can change the colour (to blue for example) by adding the "*headingcolour*" class option:


```latex
\documentclass[headingcolour={0.25,0.45,0.76}]{oxengthesis}
```


Note that the colour of subsubsection headings will be black regardless of the setting above.


## Chapter heading styles


The default style for chapter headings is simple and gives you enough space to write your content. You can take advantage of different chapter styles defined in the [memoir](https://ctan.org/pkg/memoir) package by passing the "*chapterstyle*" option. For example, the following settings:


```latex
\documentclass[chapterstyle=southall]{oxengthesis}
```

will use the "*southall*" chapter style. An example of the output is shown below:

<p align="center">
    <img src="./figures/chapterstyle-southall.png" alt="southall chapter style"
    width="350" border=1 />
</p>

&nbsp;


# Additional features


This section describes some of the additional features available in the OxEngThesis class. Refer to the official documentation of the [memoir](https://ctan.org/pkg/memoir) LaTeX package to customise your document even further.


## Figures


I use the [graphicx](https://ctan.org/pkg/graphicx) LaTeX package to include figures. You can put all figures in a "figures/" folder and you can simply include the image file directly without the file extension, as in:


```latex
\begin{figure}
    \centering
    \includegraphics[width=0.9\linewidth]{dummy_image}
    \caption
    {
        Sample image.
        \label{fig:sample_image}
    }
\end{figure}
```


the code above will insert the image file "./figures/dummy_image.png".

You can create a figure with sub plots with:


```latex
\begin{figure}[
    \centering
    \subbottom[\label{fig:subfig_example:fig1}]{
        \includegraphics[width=0.3\linewidth]{dummy_image}
    }
    \subbottom[\label{fig:subfig_example:fig2}]{
        \includegraphics[width=0.3\linewidth]{dummy_image}
    }
    \subbottom[\label{fig:subfig_example:fig3}]{
        \includegraphics[width=0.3\linewidth]{dummy_image}
    }
    \caption[The PointGrey Grasshopper2 video camera]
    {
        Caption of the figure, showing:
        \subcaptionref{fig:subfig_example:fig1} description 1,
        \subcaptionref{fig:subfig_example:fig2} description 2 and
        \subcaptionref{fig:subfig_example:fig3} description 3.
        \label{fig:subfig_example}
    }
\end{figure}
```


which will automatically produce the following output:

<p align="center">
    <img src="./figures/subplot_example.png" alt="Subplot example" width="500"/>
</p>

Note that you can directly refer to the subplot as in:


```latex
\Cref{fig:subfig_example:fig1} shows the camera ...
 ```


 which will automatically produce the text:
 

 ```
 Figure 3.2(a) shows the camera ...
 ```


 ## Tables


 You can have tables with shaded headers with:


 ```latex
\begin{table}
    \centering
    \caption{General features and specification for ...}
    \singleTableRowHeight
    \begin{tabular}{ll}

        \tableHeaderStart
        \tableHCell{Item} & \tableHCell{Description} \\
        \tableHeaderEnd

        Imaging Sensor        & Sony ICX625 2/3" progressive scan CCD \\
        Image size (pixels)   & 2448 (H) x 2048 (V)                   \\
        Pixel Size            & 3.45 \si{\micro\metre} x 3.45 \si{\micro\metre} \\
        A/D Converter         & AD9977 14-bit, dual-channel           \\
        Max frame rate        & 15 FPS                                \\
        Video Data Output     & 8, 12, 16 and 24-bit digital data     \\
        Gain \& Exposure                  & Automatic/Manual/One-Push \\
        Lens Mount            & C-mount                               \\
        Interface             & Gigabit Ethernet                      \\
        Physical dimensions   & 44 (W) mm x 29 (H) mm x 58 (L) mm     \\
        \hline 

    \end{tabular}
    \label{table:camera_specs}
\end{table}
 ```


which will produce the following output:

<p align="center">
    <img src="./figures/table_example_with_shaded_header.png" alt="Table with shaded header" width="500"/>
</p>

or you can have more complex tables as in:


```latex
\begin{table}[htb]
  \centering
  \caption{Summary of population demographics in the training and test sets}
  {
    \small
    \begin{tabular}{p{2cm} c c c c c c c c c c}
      \toprule

      Set &
      \multirowcell{2}{Number of\\subjects} &
      \multirowcell{2}{Total time\\(hours)}$^1$ &
      \multicolumn{2}{c}{Gender} &      
      \multicolumn{6}{c}{Ethnicity$^2$}  \\

      \cmidrule{4-11}
        
      &  &  & Male & Female & W & B & A & WB & WA & O  \\
      \midrule
      Training  & 15 & 216.6 & 8  & 7  & 10 & 1   & 1 & 1 & 1 & 1 \\        
      Test      & 15 & 210.0 & 10 & 5  & 10 & $-$ & 1 & 1 & 2 & 1 \\        
      \midrule        
      Total	& 30 & 426.6 & 18 & 12 & 20 & 1   & 2 & 2 & 3 & 2 \\
        
      \bottomrule
        
      \multicolumn{11}{l}
      {
        \footnotesize $^1$ Period during which both reference and estimated data were being recorded simultaneously.        
      } \\        
      \multicolumn{11}{l}
      {        
        \footnotesize $^2$ W = White, B = Black, A = Asian, WB = Mixed White \& Black, WA = Mixed White \& Asian and O = Other.        
      } \\
        
      \end{tabular}      
  } 
  \label{table:patient_demographics}
\end{table}
```


which will produce the following output:

<p align="center">
    <img src="./figures/table_example_complex.png" alt="Complex table" width="500"/>
</p>


## Cross-referencing labels


The [cleveref](https://ctan.org/pkg/cleveref) package is used to improve cross references to chapters, sections, figures and other common LaTeX labels. For example, the following text:


```latex
\Cref{chapter:literature_review} discusses .... is presented in 
\cref{chapter:dataset} with a detailed ...


The summary of the demographics for the entire set is described in
\cref{table:patient_demographics} ...


\Cref{fig:subfig_example} shows the video camera used in the study.
\Cref{fig:subfig_example:fig1} shows the camera, as opposed to 
\cref{fig:subfig_example:fig2}, which shows the lens ...
```


will produce the following output:


```
Chapter 2 discusses .... is presented in chapter 3 with a detailed ...


The summary of the demographics for the entire set is described in table 3.2 ...


Figure 3.2 shows the video camera used in the study. Figure 3.2(a)
shows the camera, as opposed to figure 3.2(b), which shows
the lens ...
```


## Glossary, acronyms and abbreviations


I use the [glossaries-extra](https://ctan.org/pkg/glossaries-extra) packages to define acronyms and automatically add the "Glossary" page in the *frontmatter*. Simply create a file with the name [glossary.tex](glossary.tex) and add all your definitions to it. For example:


```latex
\newabbreviation[longplural={heart rates},description={Heart rate}]{hr}{HR}{heart rate}
\newabbreviation[description={Respiratory rate}]{rr}{RR}{respiratory rate}
\newabbreviation[sort=SpO2, description={Peripheral oxygen saturation, as measured by a pulse oximeter}]{spo2}{\ensuremath{SpO_2}}{peripheral oxygen saturation}
```


Note that the first time you use an acronym, its full definition will be provided. For the rest of the instances, only the abbreviation will be used. The following paragraphs show how to define and use acronyms.


```latex
The standard vital signs include temperature, \ab{hr}, \ab{rr}, \ab{bp} and,
when appropriate, \ab{spo2}. The routine measurement and interpretation of 
these vital signs is a core component of the physiological assessment of most 
patients \cite{prior1977physical,goldberg2005practical} as they can provide 
critical information about the underlying state of their health. 

We included all study types looking at monitoring of \ab{hr}, \ab{bp}, \ab{rr}
 or \ab{spo2} using image analysis with comparison to a reference device. We 
 did not restrict based on clinical setting and included all age groups. Only 
 non-contact methods using cameras were included. All unpublished studies 
 found were included wherever possible to minimise publication bias.
```


which will automatically create the following output:


```
The standard vital signs include temperature, heart rate (HR), 
respiratory rate (RR), blood pressure (BP) and, when appropriate, 
peripheral oxygen saturation (SpO2). The routine measurement and 
interpretation of these vital signs is a core component of the 
physiological assessment of most patients [1,2] as they can provide 
critical information about the underlying state of their health. 

We included all study types looking at monitoring of HR, BP, RR or 
SpO2 using image analysis with comparison to a reference device. 
We did not restrict based on clinical setting and included all age 
groups. Only non-contact methods using cameras were included. All 
unpublished studies found were included wherever possible to 
minimise publication bias.
```


Note that the first time you use an acronym, its full definition will be
provided. For the rest of the instances, only the acronym will be used. The
"List of abbreviations" page will be automatically created in the frontmatter:

<p align="center">
    <kbd><img src="./figures/dphil-glossary.png" alt="Glossary page" width="350" border=1 /></kbd>
</p>



## Bibliography styles


The default style for the references is "*ieeetr*". For example, the
following LaTeX source:


```latex
...Finding reliable correspondences in two images of a scene taken from arbitrary viewpoints viewed with possibly different cameras and in different illumination conditions is a difficult and critical step towards fully automatic reconstruction of 3D scenes \cite{hartley2003multiple}...
```


will produce the following output in the content pages:


```
...Finding reliable correspondences in two images of a scene taken from arbitrary viewpoints viewed with possibly different cameras and in different illumination conditions is a difficult and critical step towards fully automatic reconstruction of 3D scenes [8]...
```


and the bibliography section will read:


```
Bibliography
...
[8] R. Hartley and A. Zisserman, Multiple view geometry in computer vision.
    Cambridge university press, 2003.
...
```


You can specify a custom bibliography style as an argument to the
"*listofreferences*" command in your "*main LaTeX source file*". For example,
the following command:


```latex
\listofreferences[apalike]
```


will use the [apalike](https://www.bibtex.com/s/bibliography-style-base-apalike/)
BibTeX style and produce the following output in the content pages:


```
...Finding reliable correspondences in two images of a scene taken from arbitrary viewpoints viewed with possibly different cameras and in different illumination conditions is a difficult and critical step towards fully automatic reconstruction of 3D scenes [Hartley and Zisserman, 2003]...
```


and the bibliography section will read:


```
Bibliography
...
[Hartley and Zisserman, 2003] Hartley, R. and Zisserman, A. (2003). Multiple
    view geometry in computer vision. Cambridge university press.
...
```


Take a look at the available styles at [The quick BibTeX guide](https://www.bibtex.com/styles/) online.



## Mark text as TODO


You can wrap text in "todo" tags, so they appear in red colour in the PDF
document. For example: 


```latex
    \todo{Add a citation to reference the latest research}
```


## Formatting source code


Often, we want to show pseudo code, source code or other verbatim content in
our document. For this, I use the
[listings](https://ctan.org/pkg/listings) package. The extra cutom
styles are defined in the class file to show 

C/C++ source code:

<p align="center">
    <img src="./figures/listing_style-c.png" alt="C/C++ source code"
    width="400" border=1 />
</p>

BASH scripts or commands:

<p align="center">
    <img src="./figures/listing_style-bash.png" alt="BASH code"
    width="400" border=1 />
</p>

or other verbatim content:

<p align="center">
    <img src="./figures/listing_style-verbatim.png" alt="Verbatim content"
    width="400" border=1 />
</p>


&nbsp;


# Troubleshooting common errors


## Text beyond page limits


When compiling a LaTeX document, you could get a warning similar to:


```
Overfull \hbox (22.49216pt too wide) in paragraph at lines 4--5
```


This often occurs when a line of your document could not fit within the designated horizontal space for text in the current page layout. The LaTeX compiler tries its best to fit text within the page limits, but sometimes it just cannot do it appropriately. This typically results in some text hanging out past the page margin due to long words, acronyms or long equations.

Sometimes, it is difficult to know where these errors occur in your document. You can add the "*debuglayout*" option to your document:


```latex
\documentclass[debuglayout]{oxengthesis}
```


A black box will be shown next to the affected lines. Below is a sample output:

<p align="center">
    <kbd>
    <img src="./figures/overfull_hbox_warning.png" alt="Overfull paragraph errors"
    width="350" border=1 />
    </kbd>
</p>


The [oxengthesis.cls](oxengthesis.cls) class file already takes advantage of other packages (such as [microtype](https://ctan.org/pkg/microtype)) to deal with common issues such as character protrusion, font expansion and inter-word spacing. I recommend you slightly rephrase your guilty sentences instead of changing the class template. This is usually the first approach many of my students take.

&nbsp;


# Suggestions and feedback


Take a look at the [oxengthesis.cls](oxengthesis.cls) file and the sample [sample_dphil_thesis.tex](sample_dphil_thesis.tex) / [sample_4yp_report.tex](sample_4yp_report.tex) documents for a more complete overview of what you can do with the provided LaTeX class template. Additionally, review the documentation of the [memoir](https://ctan.org/pkg/memoir) LaTeX package. It is quite customisable and provides many extra features not described here.

If you have any suggestions to improve the class template, don't hesitate to contact me.
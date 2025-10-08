# University of Oxford Thesis LaTeX Template

This template is a slightly re-formatted version of the _ociamthesis_ document class and thesis template developed originally by Keith A. Gillow, later modified by Sam Evans and [John McManigle](https://github.com/mcmanigle/OxThesis) before the present version. It is therefore covered by the MIT License, included in the LICENSE file.

I have added instructions for the use of this template with on and offline options below in detail; the setup for offline compiling will need some additional reading and downloads, please read through the isntallation instructions especially for LaTeXTools listed below carefully for the proper setup of Sublime Text with Skim, this will be more comprehensive.

## Quick Setup / Run in a Few Steps

If you just want to start compiling the thesis with minimal setup and if you have some experience with LaTeX follow the next steps. These are more detailed with specific notes on installations and including svg in [#Using this template]

### Overleaf Option (Simplest)

1. Go to Code > Download ZIP in this repository.

2. In Overleaf: New Project > Upload Project > select or drag the ZIP file downloaded.

3. Compile. This should generate the basic pdf file with Chapter titles and minimal content included in the template by default when downloaded.

4. Add your content and continue compiling when required. If using Zotero, sync or export .bib file and add it to the project so you can cite accordingly.

### Local Option (Requires extra setup; macOS Example)

1. Install MacTeX, Sublime Text, and Skim

Clone the repository:
```
git clone https://github.com/m-sgstyb/thesisTemplate-uniOfOxford.git
```
```
cd thesisTemplate-uniOfOxford
```
1. Open Sublime Text, install LaTeXTools and check that Skim is correctly set up to build with Sublime. A quick guide on this can be found [here](https://jj09.net/latex-with-sublimetext-and-skim/)

2. Open the full downloaded folder for the thesis template in Sublime Text. Click on a tex file, e.g. Oxford_Thesis.tex

3. Use `Cmd` + `B`, to build the PDF.

This should build the PDF with the minimal content included in the template as-is (Title page, chapters and some text, 15 pages). In Skim, `Shift` + `Cmd` + click on a pdf location will take you back to the location in source code.

To use SVG Figures *(Optional, and more detailed instructions below)*

1. Install Inkscape if using .svg figures.

2. Add the Inkscape path in LaTeXTools settings and enable -shell-escape.

> [!note]
> This quickstart allows a user to build a PDF immediately; read the full instructions below for detailed setup, cross-platform notes, and svg handling.

## Using this template
### Overleaf and Zotero
This is the simplest way to get started. If you don't yet have an account, create an [Overleaf](https://www.overleaf.com/) account.

1. Go to Code > Download zip in this repository
2. In Overleaf: New Project > Upload Project > select or drag the zip file downloaded
   
Using Overleaf allows to compile the document and track your changes online directly (when tracking changes option is toggled on).
If you use Zotero for referencing, Overleaf allows you to sync your references and builts a .bib file directly from the data compiled in Zotero. This can by synced to add any new references at any time.

### Edit Locally
If you prefer to edit LaTeX documents locally, and track through git for example, you can do so although it requires some setup.

> [!note]
> 
> Spending some time doing the below will allow the possibility to work offline on your project; I suggest periodically keeping a downloaded copy of your Overleaf document if you are using both options, or downloading it when you know you will need to be editing offline. 
> You may also just entirely prefer to work offline.


For local documents, I like [Sublime Text](https://www.sublimetext.com/) for text editing, and use [Skim](https://skim-app.sourceforge.io/) to build the PDF file in MacOS.
For Windows or Linux, different setups may be required (e.g., SumatraPDF, Okular, or Evince as PDF viewers; MiKTeX or TeX Live for LaTeX distribution).

For referencing you may still use Zotero, either by downloading the Overleaf created bib file if you started there, or you may use [BetterBibTex](https://retorque.re/zotero-better-bibtex/) in Zotero to export all your library or any subset of it to a bib file. BetterBibTex will provide a link that you need to copy and paste into the search bar to start the download. You can then just add that bib file with the name references.bib into your project root.


1. Go to Code > copy url to clipboard in this repository
2. In terminal, go to the directory where you want to keep the files
```
(base) base_path % cd your_path/your_folder_name
(base) .../your_folder_name % git clone https://github.com/m-sgstyb/thesisTemplate-uniOfOxford.git
```
Or you can fork from this base file structure and clone your own GitHub repository from the fork locally.


To locally compile in MacOS, having downloaded Sublime Text and Skim, the following is required:
1. The [MacTex Distribution](https://www.tug.org/texlive/) should be downloaded and installed
2. Follow the installation instructions for LaTeXTools at their [ReadTheDocs](https://latextools.readthedocs.io/en/latest/install/). This sets up a plugin for Sublime Text and allows you to handle build settings.

> [!important]
> The settings in Sublime Text should be updated to be able to compile locally and preview the pdf in skim.

1. In Sublime Text, go to Settings > Package Settings > LaTeXTools > Settings
2. This will open json files LaTeXTools.sublime-settings in a separate window split in two, on the left side you will see the defaults and you may edit the right hand file to override settings.

```
{
    "builder": "basic",

    "tex_directives": true,
    "viewer": "skim",
}
```
The basic builder should built with pdflatex and bibtex correctly, 

Every text file in this repository already has the line: 
```
%!TEX root = ../Oxford_Thesis.tex

```
added at the top, so when writing, you can compile the pdf directly from the text file you're working in without having to open the main Oxford_Thesis.tex file.
Any additional .tex file will require this if you have that open and wish to directly compile the project through it.

#### Building PDF
When editing locally, in Sublime Text check that Tools > Build System is set to Compile PDF, and you may use `Cmd` + `B` to build automatically.

If the build fails, you may need to change the build order by selecting Build with... or `Cmd` + `Shift` + `B` to select the basic builder (or test different builders, if needed).

In Skim, the sync setting should be enabled. Go to preferences (`Cmd` + `,`), navigate to the sync tab and check that it has Sublime Text as the preset in PDF-Tex sync support.

When the PDF is compiled in Skim, you can use `Cmd` + `Shift` + click in a location in the PDF and it will take you directly to the source location in Sublime Text for editing.

### Additional notes - svg files
Generally, adding png or pdf files as images for figures is easy with `\includegraphics` command. However, if needed, svg files may be added with the svg package. I have included in the preamble of this template the following:
```
\usepackage{svg}
```
As well as the svgpath listing all the possible locations where the svg files may be found. If adding new figure folders, this line should be updated.
Comment or remove if not using svg files, the svgpath command will allow the local compiling process to find the converted files to include in the final pdf document, but is not required if running through Overleaf.

> [!important]
> If compiling locally with svg files, the additional download of [inkscape](https://inkscape.org/release/inkscape-1.4.2/) is required.
> Sublime Text will need direction to the path where this is installed, see steps below.

1. Go again to Sublime Text: Settings > Package Settings > LaTeXTools > Settings
3. add the  builder settings and osx portion seen below to the settings file:

```
{
    "builder": "basic",
    "builder_settings": {
        "options": ["-shell-escape"],
        "aux_directory": "aux",
        "output_directory": "build",
    },
    "tex_directives": true,
    "viewer": "skim",

    "osx": {
        "texpath": "/Library/TeX/texbin:/usr/texbin:/usr/local/bin:/opt/local/bin:$PATH:/Applications/Inkscape.app/Contents/MacOS/",
    },

}
```
This adds the Inkscape path to texpath so when compiling it finds both your tex installation and the Inkscape executable as well as indicating ther -shell-escape flag which is required for svg processing locally.

If instead of MacOS, for Windows or Linux the path should be something like this:
```
    
    "windows": {
        "texpath": "C:\\Program Files\\MiKTeX\\miktex\\bin;C:\\Program Files\\Inkscape\\;C:\\Windows\\System32;$PATH"
    },

    "linux": {
        "texpath": "/usr/bin:/usr/local/bin:/snap/bin:$PATH"
    }
}
```

## Final notes

This repository also includes the splitcolor.py script from the [original template](https://github.com/mcmanigle/OxThesis); this separates the thesis into two PDFs - one with the greyscale pages and one with all the coloured pages, which would help reduce printing costs if a physical copy is needed. 


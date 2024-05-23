# University of Oxford Thesis LaTeX Template

This template is a slightly re-formatted version of the _ociamthesis_ document class and thesis template developed originally by Keith A. Gillow, later modified by Sam Evans and [John McManigle](https://github.com/mcmanigle/OxThesis) before the present version. It is therefore covered by the MIT License, included in the LICENSE file.

## Using this template
### Overleaf
If you don't yet have an account, create an [Overleaf](https://www.overleaf.com/) account.

1. Go to Code > Download zip in this repository
2. In Overleaf: New Project > Upload Project > select or drag the zip file downloaded
   
Using Overleaf allows to compile the document and track your changes online directly (when tracking changes option is toggled on)

### Edit Locally
If you prefer to edit LaTeX documents locally, and track through git
1. Go to Code > copy url to clipboard in this repository
2. In terminal, go to the directory where you want to keep the files
```
(base) base_path % cd your_path/your_folder_name
(base) .../your_folder_name % git clone https://github.com/m-sgstyb/thesisTemplate-uniOfOxford.git
```

For local documents, I like [Sublime Text](https://www.sublimetext.com/) for text editing, and use [Skim](https://skim-app.sourceforge.io/) to build the PDF file in MacOS (for Windows, using Sublime Text and [Sumatra PDF](https://www.sumatrapdfreader.org/download-free-pdf-viewer) should work).

Every text file in the repository has the line 
```
%!TEX root = ../Oxford_Thesis.tex

```
added at the top, so when writing, you can compile the pdf directly from the text file you're working in without having to open the main Oxford_Thesis.tex file.


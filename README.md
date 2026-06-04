# FNAL ECA Proposal Template

This repository facilitates the combination of user content with central style and formatting provided by FNAL.

Users should enter content in the following locations (items 4-8 cover the required appendices):
1. [info.tex](./info.tex): details for cover page, and flags to enable/disable table of contents, dots on table of contents, line numbering, biblatex, and numbered appendices
2. [packages.tex](./packages.tex): any additional packages used
3. [content.tex](./content.tex): the actual proposal content
4. [biblio.tex](./biblio.tex): references
5. [facilities.tex](./facilities.tex): facilities
6. [equipment.tex](./equipment.tex): equipment
7. [dataplan.tex](./dataplan.tex): data management plan
8. [other.tex](./other.tex): other attachments (e.g. letters of collaboration using the `\collabletter{}` command)

## References
The template is set up to use BibLaTeX+Biber, with the bibliography generated automatically from records that you dump in [references.bib](./references.bib).
If you prefer, by toggling a flag in [info.tex](./info.tex) you can opt to format your bibliography manually, with entries that you list in the `\thebibliography` block in [biblio.tex](./biblio.tex).

## Compilation

For standalone use, basic compilation is as simple as (if using Biber):
```bash
pdflatex main.tex
biber main
pdflatex main.tex
```

or (if manually formatting the bibliography):
```bash
pdflatex main.tex
```

Depending on your use of references, bibliography tools, etc., you may need to run `pdflatex` and/or `biber` multiple times (following cues from the compilation messages).

This repository can also be used as a base to create new projects on [Overleaf](https://overleaf.com).
There are several methods for this:
1. New Project -> Import from GitHub (requires linking your GitHub account)
2. Upload Project (download [zip file](https://github.com/kpedro88/FNAL_ECA_Proposal_Template/archive/refs/heads/main.zip))

This repository is set up on GitHub as a "template repository", so you can create your own repository based on it *without* needing to make a public fork, if desirable.

## Merging the signed cover page
After the lab directorate reviews and approves your proposal, you will get a signed copy of your cover page.
You will need to merge this back into your proposal before submitting in grants.gov.

This is a way to do it if you're on Linux (from https://tex.stackexchange.com/questions/497624/merging-multiple-pdf-files-without-breaking-hyperlinks), which produces a PDF file that grants.gov considers a "read-only PDF file" (so the contents will be visible in the preview PDF that grants.gov generates), and retains hyperlinks (so reviewers can click on section, citation, and URL links):
* print-to-PDF the signed cover page (this will strip the electronic signature, but apparently this is fine) to (for example) `signature_printed.pdf`
* use pdftk to merge: `pdftk A=signature_printed.pdf B=main.pdf cat A B2-end output proposal_merged.pdf`

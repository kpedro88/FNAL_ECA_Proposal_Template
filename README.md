# FNAL ECA Proposal Template

This repository facilitates the combination of user content with central style and formatting provided by FNAL.

Users should enter content in the following locations (items 4-10 cover the required appendices):
1. [info.tex](./info.tex): details for cover page, biosketch, support
2. [packages.tex](./packages.tex): any additional packages used
3. [content.tex](./content.tex): the actual proposal content
4. [biosketch.tex](./biosketch.tex): additional biosketch information (if necessary)
5. [support.tex](./support.tex): description of research (if necessary)
6. [biblio.tex](./biblio.tex): references
7. [facilities.tex](./facilities.tex): facilities
8. [equipment.tex](./equipment.tex): equipment
9. [dataplan.tex](./dataplan.tex): data management plan
10. [other.tex](./other.tex): other attachments (e.g. letters of collaboration using the `\collabletter{}` command)

## Compilation

For standalone use, basic compilation is as simple as:
```bash
pdflatex main.tex
```

Depending on your use of references, bibliography tools, etc., you may need to run `pdflatex` multiple times and/or run `bibtex` explicitly.

This repository can also be used as a base to create new projects on [Overleaf](https://overleaf.com).
There are several methods for this:
1. New Project -> Import from GitHub (requires linking your GitHub account)
2. Upload Project (download [zip file](https://github.com/kpedro88/FNAL_ECA_Proposal_Template/archive/refs/heads/main.zip))

This repository is set up on GitHub as a "template repository", so you can create your own repository based on it *without* needing to make a public fork, if desirable.

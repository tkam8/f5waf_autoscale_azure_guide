# Minimal makefile for Sphinx documentation
#

# You can set these variables from the command line.
SPHINXOPTS    =
SPHINXBUILD   = sphinx-build
SPHINXPROJ    = F5WAFAutoscaleAzureGuide
SOURCEDIR     = .
BUILDDIR      = _build
LATEX         = latex
PDFLATEX      = {{ latex_engine }}
MAKEINDEX     = makeindex

# Put it first so that "make" without argument is like "make help".
help:
    @$(SPHINXBUILD) -M help "$(SOURCEDIR)" "$(BUILDDIR)" $(SPHINXOPTS) $(O)

.PHONY: help Makefile all-pdf-ja

# Catch-all target: route all unknown targets to Sphinx using the new
# "make mode" option.  $(O) is meant as a shortcut for $(SPHINXOPTS).
%: Makefile
    @$(SPHINXBUILD) -M $@ "$(SOURCEDIR)" "$(BUILDDIR)" $(SPHINXOPTS) $(O)


{% if latex_engine == 'platex' %}
all: all-pdf-ja
all-pdf: all-pdf-ja
{% else %}
all: $(ALLPDF)
all-pdf: $(ALLPDF)
{% endif -%}
all-dvi: $(ALLDVI)
all-ps: $(ALLPS)

all-pdf-ja:
    for f in *.pdf *.png *.gif *.jpg *.jpeg; do extractbb $$f; done
    for f in *.tex; do platex -kanji=utf8 $(LATEXOPTS) $$f; done
    for f in *.tex; do platex -kanji=utf8 $(LATEXOPTS) $$f; done
    for f in *.tex; do platex -kanji=utf8 $(LATEXOPTS) $$f; done
    -for f in *.idx; do mendex -U -f -d "`basename $$f .idx`.dic" -s python.ist $$f; done
    for f in *.tex; do platex -kanji=utf8 $(LATEXOPTS) $$f; done
    for f in *.tex; do platex -kanji=utf8 $(LATEXOPTS) $$f; done
    for f in *.dvi; do dvipdfmx $$f; done

clean:
rm -f *.log *.ind *.aux *.toc *.syn *.idx *.out *.ilg *.pla *.ps *.tar *.tar.gz *.tar.bz2 *.tar.xz $(ALLPDF) $(ALLDVI)
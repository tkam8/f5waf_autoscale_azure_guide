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

.PHONY: help Makefile

# Catch-all target: route all unknown targets to Sphinx using the new
# "make mode" option.  $(O) is meant as a shortcut for $(SPHINXOPTS).
%: Makefile
    @$(SPHINXBUILD) -M $@ "$(SOURCEDIR)" "$(BUILDDIR)" $(SPHINXOPTS) $(O)


{% if latex_engine == 'platex' -%}
# latexmkrc is read then overridden by latexmkjarc
LATEX = latexmk -r latexmkjarc -dvi
PDFLATEX = latexmk -r latexmkjarc -pdfdvi -dvi- -ps-
{% else -%}
LATEX = latexmk -dvi
PDFLATEX = latexmk -pdf -dvi- -ps-
{% endif %}

%.png %.gif %.jpg %.jpeg: FORCE_MAKE
	extractbb '$@'

{% if latex_engine == 'platex' -%}
%.dvi: %.tex $(ALLIMGS) FORCE_MAKE
	for f in *.pdf; do extractbb "$$f"; done
$(LATEX) $(LATEXMKOPTS) '$<'

{% elif latex_engine != 'xelatex' -%}
%.dvi: %.tex FORCE_MAKE
	$(LATEX) $(LATEXMKOPTS) '$<'

{% endif -%}
%.ps: %.dvi
	dvips '$<'

{% if latex_engine == 'platex' -%}
%.pdf: %.tex $(ALLIMGS) FORCE_MAKE
	for f in *.pdf; do extractbb "$$f"; done
{%- else -%}
%.pdf: %.tex FORCE_MAKE
{%- endif %}
	$(PDFLATEX) $(LATEXMKOPTS) '$<'

all: $(ALLPDF)

all-dvi: $(ALLDVI)

all-ps: $(ALLPS)

all-pdf: $(ALLPDF)

clean:
rm -f *.log *.ind *.aux *.toc *.syn *.idx *.out *.ilg *.pla *.ps *.tar *.tar.gz *.tar.bz2 *.tar.xz $(ALLPDF) $(ALLDVI)
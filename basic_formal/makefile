SRCDIR   := src
BUILDDIR := build

SOURCES  := $(shell find $(SRCDIR) -type f -name \*.$(SRCEXT))

SRCEXT   := tex
TEXSRCS := $(shell find $(SRCDIR) -type f -name \*.$(SRCEXT))
TEXBUILDDIRS = build
PDFDOCS = $(shell find $(TEXBUILDDIRS) -type f -name \*.pdf)
PDFDOCSDIR := pdf

RM = rm -rf


docs: $(TEXSRCS)
	@latexmk -pdf -use-make -outdir=build \
		-xelatex $(TEXSRCS)
	@make movepdfs
	@$(RM) $(TEXBUILDDIRS)

movepdfs: $(PDFDOCS)
	@mkdir -p $(PDFDOCSDIR)
	@mv $< $(PDFDOCSDIR)

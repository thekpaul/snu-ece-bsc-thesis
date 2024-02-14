.PHONY   = all clean
SUBFILES = $(wildcard **.tex)
TEXDIST  = lua
TEXFLAGS =

all: example-ko.pdf

clean: $(wildcard **.aux **.log **.out **.toc)
	git clean -Xfd

# nobib: # TODO: Compiling without bibliography refresh
# $(TEXDIST)latex $(TEXFLAGS) $< && $(TEXDIST)latex $(TEXFLAGS) $<

.SECONDEXPANSION:
%.pdf: %.tex $$(wildcard **.tex) snu-ece-bsc-thesis.cls
	$(TEXDIST)latex $(TEXFLAGS) $<
	biber $(basename $<)
	$(TEXDIST)latex $(TEXFLAGS) $< && $(TEXDIST)latex $(TEXFLAGS) $<

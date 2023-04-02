SRCS     = $(wildcard *.groff)
TGT_PDF  = $(SRCS:.groff=.pdf)
TGT_HTML = $(SRCS:.groff=.html)
TGT_ALL  = $(TGT_PDF) $(TGT_HTML)

.PHONY: all
all: $(TGT_ALL)

# www macros
%.www.pdf: %.www.groff
	groff -pet -m www -Tpdf $< >$@

%.www.html: %.www.groff
	groff -pet -m www -Thtml $< >$@

# ms macros
%.ms.pdf: %.ms.groff
	groff -pet -m ms -Tpdf $< >$@

%.ms.html: %.ms.groff
	groff -pet -m ms -Thtml $< >$@

# clean
.PHONY: clean
clean:
	rm -f $(TGT_ALL)

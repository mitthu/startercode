SRCS     = $(wildcard *.mom)
TGT_PDF  = $(SRCS:.mom=.pdf)
TGT_HTML = $(SRCS:.mom=.html)
TGT_ALL  = $(TGT_PDF) $(TGT_HTML)

.PHONY: all
all: $(TGT_ALL)

%.pdf: %.mom
	pdfmom $< >$@

%.html: %.mom
	groff -pet -Thtml -mom $< >$@

.PHONY: clean
clean:
	rm -f $(TGT_ALL)

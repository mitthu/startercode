TEX      = latexmk
TEXFLAGS = -pdf -use-make # for xelatex, use '-pdfxe'
HTLATEX  = htlatex        # for html output

SRC      = main.tex
TGT_PDF  = $(SRC:.tex=.pdf)
TGT_HTML = $(SRC:.tex=.html)
OUTPUT   = $(TGT_PDF) $(TGT_HTML)       \
              $(wildcard *.dvi)         \
              $(wildcard *.aux)         \
              $(wildcard *.out)         \
              $(wildcard *.tmp)         \
              $(wildcard *.idv)         \
              $(wildcard *.lg)          \
              $(wildcard *.4ct)         \
              $(wildcard *.4tc)         \
              $(wildcard *.xref)        \
              $(wildcard *.css)         \
              $(wildcard *.bbl)         \
              $(wildcard *.blg)         \
              $(wildcard *.fls)         \
              $(wildcard *.fdb_latexmk) \
              $(wildcard *.synctex.gz)  \
              $(wildcard *.log)

# Compile
.PHONY: all
all: $(TGT_PDF) # $(TGT_HTML)

# Create PDF
%.pdf: $(SRC) $(wildcard *.tex)
	$(TEX) $(TEXFLAGS) $<

# Create HTML. Run: make main.html
%.html: $(SRC)
	$(HTLATEX) $<

.PHONY: clean
clean:
	rm -f $(OUTPUT)
	$(TEX) -C $(SRC)

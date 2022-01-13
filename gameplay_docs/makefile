SRC_DIR=src
TEX_COMPILER=pdflatex
OUT_DIR=./
TEX_OUT=$(OUT_DIR)/gdd.pdf

all: $(OUT_DIR) $(TEX_OUT)

$(OUT_DIR)/%.pdf: $(SRC_DIR)/%/main.tex
	latexmk $< -cd --latex='$(TEX_COMPILER)' --pdf --output-directory=$(abspath $(dir $@)) --jobname=$(basename $(notdir $@))
	# clean up the auxiliary files
	latexmk $< -c -cd --latex='$(TEX_COMPILER)' --pdf --output-directory=$(abspath $(dir $@)) --jobname=$(basename $(notdir $@))

$(OUT_DIR):
	mkdir -p $@

.PHONY=clean
clean: 
	@rm -rvf $(OUT_DIR)

# -*- coding: utf-8; -*-

.PHONY: all release tiffsep clean dist-clean

# 使用するコマンド類の定義
LATEXMK = latexmk
LATEXMK_LUALATEX = $(LATEXMK) --lualatex
#LATEXMK_PLATEX = $(LATEXMK) -r platexmkrc
#LATEXMK_UPLATEX = $(LATEXMK) -r ulatexmkrc
PDF_RM_TUC = pdf-rm-tuc --linearize --object-streams=generate \
	--newline-before-endstream
GS = gs
WGET = wget

# ターゲットのファイル名（拡張子なし）
TARGET = haranoaji-fonts-texconf2019-abstract

all: $(TARGET).pdf
release: $(TARGET)-release.pdf
#p: p$(TARGET).pdf p$(TARGET).tex
#u: u$(TARGET).pdf u$(TARGET).tex

$(TARGET).pdf: by-sa.pdf
#$p(TARGET).pdf: by-sa.pdf
#$u(TARGET).pdf: by-sa.pdf

#p%.pdf: p%.tex
#	$(LATEXMK_PLATEX) $<

#u%.pdf: u%.tex
#	$(LATEXMK_UPLATEX) $<

#p%.tex: %.tex
#	cp $< $@

#u%.tex: %.tex
#	cp $< $@

%.pdf: %.tex
	$(LATEXMK_LUALATEX) $<

%-release.pdf: %.pdf
	$(PDF_RM_TUC) $< $@

tiffsep:
	$(GS) -dSAFER -dBATCH -dNOPAUSE -sDEVICE=tiffsep \
		-sOutputFile=tiff%04d.tif $(TARGET)-rel.pdf

# EPS から PDF を生成（CC BY-SA のロゴ用）
%.pdf: %.eps
	$(GS) -dSAFER -dBATCH -dNOPAUSE -sDEVICE=pdfwrite \
		-dCompatibilityLevel=1.5 \
		-dColorConversionStrategy=/RGB \
		-dProcessColorModel=/DeviceRGB \
		-dEPSCrop \
		-sOutputFile=$@ \
		-c .setpdfwrite \
		-f $<

# CC BY-SA のロゴ EPS を取得
by-sa.eps:
	$(WGET) "http://mirrors.creativecommons.org/presskit/buttons/88x31/eps/by-sa.eps"

clean:
	-$(LATEXMK_LUALATEX) -c $(TARGET).tex
#	-$(LATEXMK_PLATEX) -c p$(TARGET).tex
#	-$(LATEXMK_UPLATEX) -c u$(TARGET).tex
#	$(RM) p$(TARGET).tex u$(TARGET).tex
	$(RM) $(TARGET).xmpdata
#	$(RM) p$(TARGET).xmpdata u$(TARGET).xmpdata
	$(RM) pdfa.xmpi
	$(RM) *~ *.dvi *.tif *.ltjruby

dist-clean: clean
	$(RM) *.pdf *.eps

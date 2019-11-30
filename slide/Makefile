# -*- coding: utf-8; -*-

.PHONY: all release tiffsep clean dist-clean

# 使用するコマンド類の定義
LATEXMK = latexmk -lualatex
PDF_RM_TUC = pdf-rm-tuc --linearize --object-streams=generate \
	--newline-before-endstream
GS = gs
WGET = wget
SED = sed
RM = rm -f

# ターゲットのファイル名（拡張子なし）
TARGET = haranoaji-fonts-texconf2019-slide

# 図ディレクトリ
FIGUREDIR = figure

# 図 PDF （拡張子なし）
GRAYTARGET = conv_to_cid ptex_to_cid luatex_to_cid

GRAYPDF = $(addsuffix .pdf,$(GRAYTARGET))
ALLTARGET = $(GRAYTARGET)
ALLPDF = $(GRAYPDF)
PDF_TEX = $(addsuffix .pdf_tex,$(ALLTARGET))

all: $(TARGET).pdf
release: $(TARGET)-release.pdf

# ターゲットの依存関係
$(TARGET).pdf: by-sa.pdf $(ALLPDF) $(PDF_TEX)

# LaTeX ソースから TeX 出力 PDF へ
%.pdf: %.tex
	$(LATEXMK) $<

# 原ノ味フォントの ToUnicode CMap を削除
%-release.pdf: %.pdf
	$(PDF_RM_TUC) $< $@

# 図 pdf (gray)
$(GRAYPDF): %.pdf: $(FIGUREDIR)/%.pdf
	$(GS) -dSAFER -dBATCH \
		-dNOPAUSE -dNOCACHE -sDEVICE=pdfwrite \
		-dCompatibilityLevel=1.5 \
		-dColorConversionStrategy=/Gray \
		-dProcessColorModel=/DeviceGray \
		-sOutputFile=$@ \
		$<

# 図 pdf_tex
$(PDF_TEX): %.pdf_tex: $(FIGUREDIR)/%.pdf_tex
	cp $< $@

# 色確認用
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
	-$(LATEXMK) -c $(TARGET).tex
	$(RM) $(TARGET).xmpdata
	$(RM) pdfa.xmpi
	$(RM) *~ *.dvi *.nav *.snm *.tif *.ltjruby

dist-clean: clean
	$(RM) *.pdf *.eps $(PDF_TEX)

<!-- -*- coding: utf-8 -*- -->
# TeXConf 2019 一般講演「原ノ味フォントと ToUnicode CMap」関連資料

[TeXConf 2019](https://texconf2019.tumblr.com/)一般講演
「原ノ味フォントと ToUnicode CMap」
関連資料です。

---

* [アブストラクト](#アブストラクト)
* [発表資料](#発表資料)

---

## アブストラクト

正式な公開版のファイルは [TeXConf 2019](https://texconf2019.tumblr.com/)
からダウンロードしてください。
ただし正式公開版ファイルは掲載に伴う加工の結果、
PDF/Aバリデーションに通過しないようです。

関連ファイルは[abstract/](./abstract/)以下にあります。
PDF/Aバリデーションに通過するPDFもこちらです。

### ソースファイル

* [Makefile
](./abstract/Makefile)

    - 公開用アブストラクト関連ファイルをビルドするための Makefile

* [haranoaji-fonts-texconf2019-abstract.tex
](./abstract/haranoaji-fonts-texconf2019-abstract.tex)

    - 公開用アブストラクトのソース

* [pdfa.xmp
](./abstract/pdfa.xmp)

    - PDF/A および CC BY-SA 4.0 用の XMP データ

* [pdfa.xmp.diff
](./abstract/pdfa.xmp.diff)

    - [pdfx パッケージ](https://ctan.org/pkg/pdfx)
      オリジナルの `pdfa.xmp` からの差分ファイル

### 出力

### make 環境

* LuaTeX 1.10.0 (TeX Live 2019/Cygwin)
* Ghostscript 9.27
* [pdf-rm-tuc](https://github.com/trueroad/pdf-rm-tuc) 1.0.0
* [原ノ味フォント](https://github.com/trueroad/HaranoAjiFonts) 20190824

など

### ファイル

* 公開用アブストラクト PDF

    + [haranoaji-fonts-texconf2019-abstract-release.pdf
](./abstract/haranoaji-fonts-texconf2019-abstract-release.pdf)

        - LuaLaTeX が出力した PDF から、
          原ノ味フォントの ToUnicode CMap を
          [pdf-rm-tu](https://github.com/trueroad/pdf-rm-tuc)
          で削除した、リリース版PDF
        - [veraPDF](https://verapdf.org/) 1.15.8 による
          PDF/A バリデーションに通過します

    + [haranoaji-fonts-texconf2019-abstract.pdf
](./abstract/haranoaji-fonts-texconf2019-abstract.pdf)

        - LuaLaTeX が出力した PDF
        - [veraPDF](https://verapdf.org/) 1.15.8 による
          PDF/A バリデーションに通過します

## 発表資料

発表資料を鋭意制作中に台風19号の影響でTeXConf2019が中止となりました。
中止により締め切りがなくなってしまった？ため制作が停滞しておりましたが、
11月30日に公開します。

元々は講演時間に合わせて後でスライド数を減らすつもりでしたが、
講演がなくなってしまったため減らしておりません。
一部に10月12日以降の状況も含まれております。

* [PDF](./slide/haranoaji-fonts-texconf2019-slide-release.pdf)
* [ソースファイルなど](./slide/)

### 図

発表資料で使用している[図のファイル](./slide/figure/)は、
Inkscape 0.92.4 で作図し、以下のように出力したものです。

Inkscape 本来の保存形式のファイル名が `名前.svg` の場合、
名前を付けて保存で PDF を選び、`名前.pdf` という名前で保存します。
出てきたダイアログで、

* PDFバージョン制限
    * PDF 1.5 （デフォルト）
* Text output options
    * Omit text in PDF and create LaTeX file
* フィルターエフェクトをラスタライズする
    * チェック外す
* ラスタライズ解像度 (dpi)
    * 96 （デフォルト）
* 出力ページサイズ
    * ドキュメントのページサイズを使用（デフォルト）
* 裁ち落し/マージン (mm)
    * 0.0 （デフォルト）
* オブジェクトのエクスポートを ID で制限する
    * 空欄（デフォルト）

これで、
`名前.pdf`
と同時に
`名前.pdf_tex`
ができます。

## License

Copyright (C) 2019 Masamichi Hosoda.

License: CC BY-SA 4.0

[LICENSE](./LICENSE) をご覧ください。

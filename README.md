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

お待ちください。

## License

Copyright (C) 2019 Masamichi Hosoda.

License: CC BY-SA 4.0

[LICENSE](./LICENSE) をご覧ください。

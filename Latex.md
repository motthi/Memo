# Latexに関するメモ
## Latexのインストール
- [Tex Wiki](https://texwiki.texjp.org/)
- [LaTex プログラムコードを載せる時のプラグインListingsのインストール](https://kshi-kshi.hatenadiary.org/entry/20110219/1298117610)
## Latexの編集
- [VSCodeで最高のLatex環境を作る](https://qiita.com/Gandats/items/d7718f12d71e688f3573)  

## BibTex
- 参考文献を挿入する箇所に以下のコマンドを記入する  
```
\bibliography{ref}  
\bibliographystyle{junsrt}
```

|  欧文用  |  和文用  |  特徴  |
| ---- | ---- |  ----  |  
|  plain  |  jplain  |  参考文献をアルファベット順で出力する  |  
|  unsrt  |  junsrt  |  参考文献を引用された順で出力する  |  

- ref.bibに文献情報を記入する  

- 1回コンパイルする  
```
platex "file.tex"
```  

- データベースの参考文献を反映させる  
`bibtex "file"`（欧文の場合）  
または  
`pbibtex "file"`（和文の場合）  

- 3回コンパイルする  

- 参考  
[BiBTeXとは](https://qiita.com/SUZUKI_Masaya/items/14f9727845e020f8e7e9)  
[jbibtex　エラー: I found no \citation commands ---](https://behavior-analysis.at.webry.info/200906/article_2.html)

### IEEEtransを使ったときに著者が-----となる
同じ著者の論文が連続すると著者名が"-----"となる．  

- 対策方法  
まずbibファイルに以下のコマンドを書く．  
```
@IEEEtranBSTCTL{IEEEexample:BSTcontrol,
  CTLdash_repeated_names = "no"
}
```
次にTexファイルの本文の中に`\bstctlcite{IEEEexample:BSTcontrol}`と書く．  
(begin{document}の直後）

プリアンプルに以下を記入する
```
\makeatletter
\def\bstctlcite{\@ifnextchar[{\@bstctlcite}{\@bstctlcite[@auxout]}}
\def\@bstctlcite[#1]#2{\@bsphack
\@for\@citeb:=#2\do{%
\edef\@citeb{\expandafter\@firstofone\@citeb}%
\if@filesw\immediate\write\csname #1\endcsname{\string\citation{\@citeb}}\fi}%
\@esphack}
\makeatother
```

- 参考  
[IEEEtran.bstで著者名が線になるのを防ぐ](http://kawaiihaseigi.blogspot.com/2015/02/ieeetranbib.html)  
[Is it normal for BibTeX to replace similar author names with "------"?](https://tex.stackexchange.com/questions/29381/is-it-normal-for-bibtex-to-replace-similar-author-names-with)  
[How to Use the IEEEtran BIBTEX Style](http://tug.ctan.org/biblio/bibtex/contrib/IEEEtran/IEEEtran_bst_HOWTO.pdf)  

## 文書内リンクの有効化
プリアンプルに以下を記述する  
(`\usepackage[dvipdfmx]{hyperref,graphicx}`も忘れずに)  
```
\usepackage[dvipdfmx]{hyperref,graphicx}
% for hyperref
\usepackage{pxjahyper}
\hypersetup{
	colorlinks=false, % リンクに色をつけない設定
	bookmarks=true, % 以下ブックマークに関する設定
	bookmarksnumbered=true,
	pdfborder={0 0 0},
	bookmarkstype=toc
}
```

- 参考  
[【Tex】卒論修論には是非ハイパーリンク機能をつけよう](https://ossyaritoori.hatenablog.com/entry/2016/11/11/%E3%80%90Tex%E3%80%91%E5%8D%92%E8%AB%96%E4%BF%AE%E8%AB%96%E3%81%AB%E3%81%AF%E6%98%AF%E9%9D%9E%E3%83%8F%E3%82%A4%E3%83%91%E3%83%BC%E3%83%AA%E3%83%B3%E3%82%AF%E6%A9%9F%E8%83%BD%E3%82%92%E3%81%A4)


## コマンド
- ビルド  
  `platex ex1.tex`  
- pdfファイルの生成  
  `ptex2pdf -l ex1`  
  
## Visual Studio Codeでのショートカット
- ビルド  
  `Ctrl + Alt + B`
- プレビュー生成  
  `Ctrl + Alt + V`  
  
## 圧縮せずにPDFに出力
Robomechではじかれることがある．  
圧縮せずにPDFに出力すれば可能．  
`dvipdfmx file.dvi -z 0`


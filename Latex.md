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

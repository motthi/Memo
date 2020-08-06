# Jupyter
## Jupyter Notebook
### 拡張機能
- [Jupyter notebookのextensionを使ってオレオレPythonチートシートを作る](https://qiita.com/hanon/items/1d00a1eac026af0389fb)

### 
立ち上げようとすると，下のようなエラーが出ることがある．  
```
sqlite3.OperationalError: 指定されたプロシージャが見つかりません。
```
sqlite3.dllの読み込みが正常にできていないから（？）  
Windows用のSQLiteをダウンロードし，`C:\Windows\System32`に入れる．  
- [SQLite Download Page](https://www.sqlite.org/download.html)  

# Jupyter
## Jupyter Lab
## Execute Time
[jupyterlab-execute-time](https://github.com/deshaw/jupyterlab-execute-time)
jupyter_serverのバージョンを変更する必要があるかも．
`pip install jupyter_server==1.6..4`

## Jupyter Notebook
### 拡張機能
- [Jupyter notebookのextensionを使ってオレオレPythonチートシートを作る](https://qiita.com/hanon/items/1d00a1eac026af0389fb)

### 起動時のエラー
立ち上げようとすると，下のようなエラーが出ることがある．  
```
sqlite3.OperationalError: 指定されたプロシージャが見つかりません。
```
sqlite3.dllの読み込みが正常にできていないから（？）  
Windows用のSQLiteをダウンロードし，`C:\Windows\System32`に入れる．  
- [SQLite Download Page](https://www.sqlite.org/download.html)  

### Slackへの終了通知
```
def slack_notify(msg = 'Finished'):
    slack_user_id = '{user_id}'
    slack_webhook_url = '{webhook_url}'
    requests.post(slack_webhook_url, json={"text":f"{msg}"})
```

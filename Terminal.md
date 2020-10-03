# Terminal
## Windows
### 処理時間計測
Power Shellで実行する．  
{}の中に処理時間を計測したいコマンドを記入する．
```
powershell -Command "Measure-Command {.\a}"
```

ミリ秒のみ取り出したい場合
```
powershell -C (Measure-Command {.\a}).TotalMilliseconds
```

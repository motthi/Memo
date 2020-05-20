# Raspberry pi
## Webページ公開の手順  
- [Raspberry PiでWebページ公開](https://qiita.com/rockhopper-penguin/items/66a8104bb1e4559ec144)  
  ファイアウォールの設定で公開鍵認証で使うポートも許可しないと，SSH接続できなくなる．  
## apt-get updateで失敗
- DHCPを再取得する  
  無線LANなら`sudo dhclient wlan0`  
  有線LANなら`sudo dhclient eth0`  

- nameserverを編集する  
  `/etc/resolv.conf`を編集する  
  ```
  nameserver xxx.xxx.xxx.xxx
  ```

- Mirrorサーバーを使う  
上手くいったためしがない．

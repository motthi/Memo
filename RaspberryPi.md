# Raspberry pi
## 初期設定  
- [Raspbian ユーザ名変更の個人的に「正しい」と思うやり方](https://jyn.jp/raspberrypi-username-change/#i-3)  
- [Raspberry Pi に固定IPアドレスを割り当てる方法（Raspbian Jessie）](https://qiita.com/marie_khr/items/b088ffb252a92eee8f5d)  
- [Raspberry Piに公開鍵認証を使ってssh接続する](https://tool-lab.com/raspi-key-authentication-over-ssh/) 
- [RaspberryPiにDockerを構築する](https://qiita.com/d0d0npa/items/0f2d6af2618618982723)
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

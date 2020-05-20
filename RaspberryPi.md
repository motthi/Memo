# Raspberry pi
## apt-get updateで失敗
- DHCPを再取得する  
無線LANなら`sudo dhclient eth0`  
有線LANなら`sudo dhclient wlan0`  

- nameserverを編集する  
`/etc/resolv.conf`を編集する  
```
nameserver xxx.xxx.xxx.xxx
```

- Mirrorサーバーを使う  
上手くいったためしがない．

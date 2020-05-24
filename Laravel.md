# Laravel
## LaravelをDocker上で構築する
ディレクトリ構成  
```
.  
├── docker
│   ├── ngnix
│   │   └── ngnix.conf
│   ├── php
│   │   └── Dockerfile
│   └── setup.sh  
├── server  
├── docker-compose.yml
└── README.md
```

serverはGitからクローンする．  
クローン後，ディレクトリ名を`server`に変える．  
```
git clone https://github.com/laravel/laravel.git laravel

```

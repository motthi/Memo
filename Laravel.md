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

- [Dockerを使ってLaravel開発環境構築](https://qiita.com/A-Kira/items/1c55ef689c0f91420e81)
- [Laravelの実行環境をDockerで構築する](https://qiita.com/yoshiplur/items/fa875e111f908cd8786c)

# React-Django-Docker
ReactとDjangoを用いてアプリを開発する用のdocker-composeです。

##　実行には下記コマンドを実行

### 最初の docker-compose up -d --build 実行時にコメントアウトが必要なもの

command: sh -c "cd api && python3 manage.py runserver 0.0.0.0:8000"
command: sh -c "cd frontend && yarn start"

1.  docker-compose up -d --build
2.  docker-compose exec api /bin/bash
3.  mkdir api && cd api
4.  django-admin startproject config . && django-admin startapp todo
5.  exit
6.  docker-compose exec node /bin/bash
7.  npx create-react-app frontend
8.  cd frontend
9.  yarn add axios bootstrap@4.6.0 reactstrap@8.9.0 --legacy-peer-deps
10. exit
11. ここでコメントアウトをはずす。
12. docker-compose up -d --build
13. package.json に"proxy": "http://api:8000",を追記。 settings.py に ALLOWED_HOSTS = ["api"]と CORS_ORIGIN_WHITELIST = [
    'http://node:3000'
    ]を追記。
14. docker-compose down

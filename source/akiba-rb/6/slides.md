# Akiba.rb #6

## in Akiba code
by Ryoji Yoshioka / @ojiry
---
## Thanks Akiba code :pray:
[Akiba code](https://akibacode.blogspot.jp/) is the good place :+1:
---
## About me
* Ryoji Yoshioka (@ojiry)
* Akiba.rb Organizer
* Rails Programer
* My editor is Neovim
---
### Ran Itabashi City Marathon on Sunday
![itabashi-city-marathon](images/itabashi-city-marathon.png)
---
## 今日やったこと
* 勉強会で使う Slack Team の統合
* 発表資料（これ）の作成
* ユーザ登録 API の実装
***
## ユーザ登録 API の実装
---
## リソースは？
* /users
* /registrations
* /accounts
---
## こんな感じにした
```sh
$ curl -i -X POST http://localhost:3000/users
```
---
## 取り敢えず 201 のコード返す
```sh
$ curl -i -X POST http://localhost:3000/users
HTTP/1.1 201 Created
...
```
---
## パラメータ
* email, password
* 取り敢えず最小限で
* Strong Parameters に追加
---
## Model は面倒なので puts するだけ
```
$ curl -i -X POST -d "email=hoge@example.com&password=123456&invalid=hoge" http://localhost:3000/users 

Started POST "/users" for 127.0.0.1 at 2017-03-21 20:15:28 +0900
Processing by UsersController#create as */*
  Parameters: {"email"=>"hoge@example.com", "password"=>"[FILTERED]", "invalid"=>"hoge"}
Unpermitted parameter: :invalid
<ActionController::Parameters {"email"=>"hoge@example.com", "password"=>"123456"} permitted: true>
Completed 201 Created in 1ms
```
---
## Rails なので JSON にも当然対応
```
$ curl -i -X POST -H 'Content-type: application/json' -d '{"email": "hoge@example.com", "password": "123456"}' http://localhost:3000/users

Started POST "/users" for 127.0.0.1 at 2017-03-21 20:22:46 +0900
Processing by UsersController#create as */*
  Parameters: {"email"=>"hoge@example.com", "password"=>"[FILTERED]", "user"=>{"email"=>"hoge@example.com", "password"=>"[FILTERED]"}}
Unpermitted parameter: :user
<ActionController::Parameters {"email"=>"hoge@example.com", "password"=>"123456"} permitted: true>
Completed 201 Created in 1ms
```
---
## と言いたかったけどアレ？w
```
  Parameters: {"email"=>"hoge@example.com", "password"=>"[FILTERED]", "user"=>{"email"=>"hoge@example.com", "password"=>"[FILTERED]"}}
```
---
## 確か wrap_parameters とかなはず
が、時間が :scream:
***
## 今後やりたい事
* https://developer.github.com/v3/
* バージョニング
* 複数の認証方式
---
## Thanks :clap:

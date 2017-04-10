# Akiba.rb #7

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
### Joined Quipper from April 1, 2017.
![github-profile](images/github-profile.png)
---
## 腐らない Gemfile の作り方

```ruby
source "https://rubygems.org"

gem "fresh_gem"

group :development do
  gem "clean_gemfile"
end
```
---
## あなたの Gemfile 新鮮ですか？
:spaghetti: :yum: :sushi:
---
## Gemfile が腐ると...
* バージョンをあげれない
* 新しい機能が使えない
* バグが直らない
* モンキーパッチ地獄
---
## 問題だらけ :cold_sweat:
---
## なぜ腐るのか？
---
## 腐る原因その1
### 大量の Gem を登録
---
## 何個あった？
```sh
$ cat gemfile | grep gem | wc -l
```
---
## その数がプロジェクトで管理する必要がある Gem の数だ
---
## Gem はメンテナがいる？
---
## そのふざけた幻想をぶち殺す
---
## 有名な Gem も開発は止まります
* https://github.com/ryanb/cancan 
* https://github.com/pluginaweek/state_machine
---
## 有名じゃない Gem はもっと止まります
* https://github.com/ojiry/skmz
---
## そして止まる Gem の更新
### 別の Gem に切りかえようにも依存範囲が...
---
## Forked repository :scream:
---
## なんでも Gem で解決するのはよくない
* Gem を追加する前に胸に手を当てて考えよう
* その機能は自分でも実装出来るんじゃないか
* 開発が活発で利用者も多いか
---
## 腐る原因その2
### Gemfile の断捨離
---
## 使ってないコードがあったら？
---
## 当然削除しますよね
---
## 使ってない Gem があったら？
---
## 削除...してます？
---
## 息の長いプロジェクトだと不要な Gem が多い
* 特に development, test グループ
* 追加はしても削除はしない
* 本当のゴミは Gemfile にある
---
## Gemfile にかかれている Gem = 管理する必要のある Gem
---
## 不必要な Gem は削除しましょう :put_litter_in_its_place:
---
## 腐る原因その3
### モンキーパッチ :monkey:
---
## きみはモンキーパッチが得意なフレンズなんだね
---
## 君とは友達になれそうにない :no_good:
---
## それが有効な場合もある
### が、そうじゃない事が多い
---
## よくあったパターン
* モンキーパッチがある
* 元の Gem の処理を変えている
* モンキーパッチのせいで Gem を更新できない
* Gem が腐る
* 心も腐る
---
## まとめ
---
## Gemfile は生き物
---
## なるべく最新の状態に保つ
---
## 追加・更新・削除に注意を払う
---
## 使ってる Gem の管理は自分達の責任
---
## 新鮮な Gemfile で楽しい開発ライフを :smile:
---
## Thanks :clap:

# git-command

毎回忘れて，そのたびに調べてたけど面倒なので，まとめる

キーワードだけ書いてるので，それで思い出せなければぐぐる

## ブランチ
```bash
# git checkout は非推奨
# git switch を使う
# checkout = switch + restore らしい

git switch -c <new b>  # bブランチを作成して移動
git switch -  # 一つ前のブランチに移動
git switch <b>  # bブランチに移動
git branch -m <b> <new b>  # bブランチの名前を変更
git branch -D <b>  # bブランチを削除
git push <remote> <b>  # bブランチをリモートにpush
git fetch --prune  # リモートのbranch情報をローカルに反映（PRをマージした後とか）
git fetch origin <remote b>  # リモートあるブランチ（自分以外の人が作ったやつとか）をローカルにfetch
git merge --no-ff <remote>/<remote b>  # 作業中のブランチに，remoteのブランチを取り込む
```

## 設定
```bash
git config --list
# 初期設定
git config --global user.name "hoge"
git config --global user.email hoge@piyo.com
```

## 一時退避
```bash
git stash
git stash save "msg"
git stash list
git stash pop  # 最新のstashを戻して削除．pop = apply + drop
git stash apply  # stashを戻すだけ．stashは残る
git stash drop  # stashを消す
```

## 取り消し
```bash
git reset
git revert
git commit --amend  # コミットを取り消し
```
ref（resetとrevertの違い）
- https://qiita.com/Sammy_U/items/e37c7242544fd1da81be
- https://qiita.com/S42100254h/items/db435c98c2fc9d4a68c2

## 削除
```bash
git rm
git rm --cached <file>  # 一度addしたファイルを追跡対象外にする．これしないと，gitignore効かない
```

## タグ
```bash
git tag
git tag -a <tag name> -m <msg>
git push <remote> <tag name>
git push <remote> --tag
```
ref
- https://qiita.com/MahoTakara/items/3a7fe950e91b8e51f8b8
- https://qiita.com/Kasumin0123/items/5aeb3bae22723bc3bb26

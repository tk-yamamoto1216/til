# リモートリポジトリ （GitHub） を新規追加する

```git
git remote and origin <GitHub の URL>
```

GitHub のリモートリポジトリを登録するよ  
これをしておくと origin という名前で GitHub のリモートリポジトリを呼び出すことができる  

### なぜ origin なのか？

origin　とはリモートリポジトリのショートカット名
git の慣用句のようなもの  
git clone をしたときの元々のリモートリポジトリを git ではオリジンというショートカットに割り当てる  

# リモートリポジトリ（GitHub）へ送信する  

```git
git push <リモート名> <ブランチ名>
git push origin master
```
ローカルリポジトリの内容をリモートリポジトリに送ることを「プッシュ」という
origin　とはリモートリポジトリのショートカット名  
master はデフォルトのブランチ名  

```git
git push -u origin master
```
-u というオプションを初回に付けておくことで、次回以降 git push のみで push できるようになる  

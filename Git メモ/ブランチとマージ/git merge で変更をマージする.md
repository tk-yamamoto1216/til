### マージとは、他の人の変更内容を取り込む作業のこと

```git 
git merge <ブランチ名>
git merge <リモート名/ブランチ名>
``` 

```git
git merge origin/master
```
GitHubにある master ブランチの内容を自分の作業中のブランチにマージする  

### マージには3種類ある

#### Fast Forword : 早送りになるマージ  

ブランチが枝分かれしなかった時はブランチのポインタを前に進めるだけ  

#### Auto Merge : 基本的なマージ  

枝分かれして開発してた場合、マージコミットという新しいコミットを作る  
Auto merge の新しいコミットファイルは Parent を2つ持っている  

#### Conflict : 複数人で同じ箇所の変更を別々に変更してしまった時に起こる

次で解説します

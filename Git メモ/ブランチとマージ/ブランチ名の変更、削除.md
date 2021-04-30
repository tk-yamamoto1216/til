### ブランチ名を変更する

```git
git branch -m <ブランチ名>
```

ブランチ名を new_branch としたい時は

```git
git branch -m new_branch
```

とする。  

### ブランチを削除

```git
git branch -d <ブランチ名>
```

feature というブランチを削除したい時は、

```git
git branch -d feature
```  

-d をつけると、master にマージされていない変更が残ってる場合削除しない   

### ブランチを強制削除

```git
git branch -D <ブランチ名>
```

-D をつけると、master にmaster にマージされていない変更が残っていても削除する  

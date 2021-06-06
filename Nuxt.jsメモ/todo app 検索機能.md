## ① dataにfind_flgを追加

```
data: function() {
  return {
    content: '',
    find_flg: false
  }
},
```

## ② findボタンにクリックイベントを設定してmethodsのfindを呼び出す

```
<button @click="find">find</button>
```

## ③ findボタンが押されたらfind_flgをtrueにします


```
find: function() {
  this.find_flg = true;
},
```

## ④ computedにdisplay_todosを設定し、find_flgがtrueの場合は新たにarrという配列を用意

```
display_todos: function() {
  if(this.find_flg) {
    var arr = [];
    var data = this.todos;
    data.forEach(element => {
      if(element.content.toLowerCase() == this.content.toLowerCase()) {
        arr.push(element);
      }
    });
    return arr;
  } else {
    return this.todos;
  }
}
```

+ element には検索された単語の情報が格納されてる
+ toLowerCase() メソッドは、呼び出す文字列の値を小文字に変換して返す

```
if(element.content.toLowerCase() == this.content.toLowerCase())
```
element.content.toLowerCase　（検索フォームに入力された内容）　と、
this.content.toLowerCase　（todo リストに登録されてる内容 ）　が一致するかチェック

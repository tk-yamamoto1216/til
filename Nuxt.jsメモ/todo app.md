 # index.vue
```
<p><input type="text" name="content" v-model="content"/></p>
    <div>
      <button @click="insert">save</button>
      <button>find</button>
    </div>
    <ul>
      <li v-for="(todo, index) in todos" :key="index">
        <span>{{ todo.content }}</span><span>({{ todo.created }})</span><span>×</span>
      </li>
    </ul>

```

# index.js

```
import Vuex from 'vuex';

const createStore = () => {
    return new Vuex.Store({
        state: () => ({
            todos: [
                {content: 'hogehoge', created: '2019-03-31 15:30'}, 
                {content: 'fugafuga', created: '2019-03-31 16:00'}
            ]
        }),
        mutations: {
            insert: function(state, obj) {
                var d = new Date();
                var fmt = d.getFullYear() 
                            + '-' + ('00' + (d.getMonth() + 1)).slice(-2) 
                            + '-' + ('00' + d.getDate()).slice(-2) 
                            + ' ' + ('00' + d.getHours()).slice(-2) 
                            + ':' + ('00' + d.getMinutes()).slice(-2);
                state.todos.unshift({
                    content: obj.content,
                    created: fmt
                })
            },
            remove: function(state, obj) {
                for(let i = 0; i < state.todos.length; i++) {
                    const ob = state.todos[i];
                    if(ob.content == obj.content && ob.created == obj.created) {
                        alert('remove ' + '"' + ob.content + '"');
                        state.todos.splice(i, 1);
                        return;
                    }
                }
            }
        }
    })
}

export default createStore;
```

## index.js 解説

### Vuex とは

VuexはVue.jsアプリケーションのための状態管理パターン+ライブラリです。  
すべてのページで利用するデータをまとめて保管するための仕組みがVuex  


### state の中身

```
state: () => ({
  todos: [
      {content: 'hogehoge', created: '2019-03-31 15:30'}, 
      {content: 'fugafuga', created: '2019-03-31 16:00'}
  ]
}),
```

+ todos という配列を作る
+ この中にtodoを追加したり削除したりする
+ todoの内容 (content) と 日時 (created) の2つのプロパティを持たせる  

### mutations の中身

#### mutations とは

+ ストアの状態は、ミューテーションによってのみ変更される
+ ミューテーションはタイプとハンドラを持ち、ハンドラ関数は直接実行することができない
+ store.commitをタイプを指定して呼び出す必要がある
+ ハンドラ関数は非同期処理を行なってはならない
+ ハンドラ関数は**第一引数に state を常に受け取る**
+ モジュール内で定義されていれば、モジュールのローカルステートを受け取る
+ 指定されていれば第二引数に payload を受け取ります。

stateの値を変更するための処理をmutationsの中に書きます。  

```
insert: function(state, obj) {
    var d = new Date();
    var fmt = d.getFullYear() 
                + '-' + ('00' + (d.getMonth() + 1)).slice(-2) 
                + '-' + ('00' + d.getDate()).slice(-2) 
                + ' ' + ('00' + d.getHours()).slice(-2) 
                + ':' + ('00' + d.getMinutes()).slice(-2);
    state.todos.unshift({
        content: obj.content,
        created: fmt
    })
},
```

insertでは、state（todos）と入力されたtodoを引数として、
入力されたtodoと入力された時間（fmt）を配列todosに追加する

```
remove: function(state, obj) {
    for(let i = 0; i < state.todos.length; i++) {
        const ob = state.todos[i];
        if(ob.content == obj.content && ob.created == obj.created) {
            alert('remove ' + '"' + ob.content + '"');
            state.todos.splice(i, 1);
            return;
        }
    }
}
```
removeでは、insertと同じくstate（todos）と入力されたtodoを引数として、
入力されたtodoの内容と日時が配列todosのtodoと一致した場合に、
「remove (todoの内容)」というalertを表示させ、配列todosから削除します。

## todosの表示

```
<ul>
  <li v-for="(todo, index) in todos" :key="index">
    <span>{{ todo.content }}</span><span>({{ todo.created }})</span><span>×</span>
  </li>
</ul>
```
```
computed: {
    ...mapState(['todos'])
  }
```

mapStateを使うことで、scriptの中ではthis.stateの名前、templateでは{{stateの名前}}でstateの値を利用することができます。


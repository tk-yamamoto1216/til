```
remove: function(state, payload) {
    for(let i = 0; i < state.todos.length; i++) {
        const ob = state.todos[i];
        if(ob.content == payload.content && ob.created == payload.created) {
            alert('remove ' + '"' + ob.content + '"');
            state.todos.splice(i, 1);
            return;
        }
    }
}
```

+ state.todos.length は todos の数
+ const ob = state.todos[i];　は削除選択されたtodo

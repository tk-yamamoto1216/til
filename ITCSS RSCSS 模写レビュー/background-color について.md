- background での背景色指定について
  背景色しか指定しないなら background-color を使用した方がミスが少ないと思います。

  - 参考：https://memo.itsysgroup.com/?p=925

background を使うと一括で指定できるようになる

```
#TableA{
 background: #ffffff url(***.gif) repeat-y right top fixed;
}
```

なので color しか指定しない時は 

```
backgroud-color: #ffffff;
```
でいい

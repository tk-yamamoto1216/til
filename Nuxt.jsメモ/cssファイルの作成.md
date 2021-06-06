① pagesフォルダにstyle.cssを作成  

pages/style.css
```pages/style.css
.container {
    width: 400px;
    margin: 100px auto;
    text-align: center;
}

h1 {
    font-size: 32pt;
}

```

② フォルダ直下にあるnuxt.config.jsのcssの部分を、以下のように修正

```
input {
  css: [
    'pages/style.css'
  ]

```

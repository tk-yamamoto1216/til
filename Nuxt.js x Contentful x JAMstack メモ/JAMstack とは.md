# JAMstack とは

+ JamstackのJamは **JavaScript / APIs / Markup** の 頭文字です  
+ JavaScriptでAPIをたたいてMarkupを配信することを意味しています
+ パフォーマンスの高さとセキュリティの高さがうたわれています
+ Web サーバに依存しない → サーバレスなサイト！
+ 事前にビルドされた静的なファイルからJavaScript経由でAPIをコールする
+ 静的ファイルをCDNから配信している
+ ユーザごとにコンテンツの出し分けがないようなアプリは一番はまります

# Jamstack の構造

![image](https://user-images.githubusercontent.com/64131315/120884696-9457cd00-c61f-11eb-8433-f16feef896ef.png)

+ HTMLを取得して表示するだけ 
+ 静的なコンテンツを配信するだけなので高速

## Javascript 

+ すべての動的プログラミングはクライアント（ブラウザ）の JavaScript が行う
+ クライアントの JavaScript は特定の方法を指さない
+ フレームワークやライブラリを使ってもよい

## API

+ すべてのサーバの処理は Web API を通じて行います
+ JavaScript が Web API を呼び出し、データの送受信を行います
+ サードパーティのサービスを利用したい場合は Web API を通じて利用

## Markup

+ マークアップのテンプレートはデプロイ時に事前ビルドされているべき
+ たいていはサイトジェネレータを使うか、ウェブアプリのビルドツールを使うか
+ 


# Jamstackでよく使われるサービス

## ヘッドレスCMS

投稿システムの構築
**API の構築をこれで行う**  

Contentful や microCMS など、、、  

## 静的サイトジェネレーター

+ HTMLを生成するライブラリが必要  
+ ビルド時にAPIをたたいてそのデータを取り込める必要がある  
+ そういった機能を備えた静的サイトジェネレーターが必要  
+ ReactベースのGatsbyやNext.js、VueベースのNuxtやGridsomeなど  

## ホスティングサービス  

+ 生成した静的コンテンツを配信できるサービス  
+ NetlifyやNow、Firebase Hosting　など  
+ 

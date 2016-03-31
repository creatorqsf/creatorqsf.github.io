---
layout: default
title: あなたの大切な家を、Google Mapsのみで確認する業者から守りたいの…
---

今宵の月はどうでしょう。こんばんは、[@CreatorQsF](http://f.9en.co/?move=mainSns)です。  
突然ですが、[Googleマップの表示ミスでトルネード被害から再建された家が解体されるというアクシデントが発生 - GIGAZINE](http://gigazine.net/news/20160328-house-torn-down-google-map-mistake/)  
このニュースをご存知でしょうか。

非常に悲しいニュースです。あなたの大切なマイホーーーーーー無。悲しい変換ミス。いえほんとに悲しんでます。  
**私はこのニュースについてよく知らないのですが**、もしかしたらGoogle Mapsでトルネードによって表示する位置が変わってしまったのかなぁ、そんな感じなのでしょうかね。

**なんかニュースを取り違えてる気がしますが**、これをみてピンときました。もしかしてGoogle Mapsで表示する位置が変わってないかどうか調べるコマンドってのは、需要があるんじゃないか、なんて(ありません。

そこでどうしてもマイホームを守るためGoogle Mapsで自宅が変わってないかどうか調べるコマンドを作る必要に迫られたため、作りました。  
なおコードはものすごく汚いです。原因は書いている時に住所という大事な情報をそのまま保存するわけにはいかないと気づき、さらにAPI Keyを保存するためにpemの発行などを行うコードを書き足し書き足ししたので、**main関数しかないくせに200行もあるコードとなっております**。っていうかこれ絶対メンテナンス出来ない。汚すぎる(普段はしっかり設計決めてから書き始めるんですがさすがにこんな遊び…じゃなかった、ニッチなものに時間かけられないですからね…。)

***

## インストールとか

`go get github.com/Qs-F/protect-yourhome`

githubでrelease切る気はないので自分でbuildして使ってください。

`protect-yourhome -k YOUR_GOOGLE_MAP_GEOCODING_API_KEY -a "YOUR_HOME_ADDRESS"`

こんな感じで住所とか登録できます。errorとかはものすごくテキトウなのでご勘弁。  
なおcronとかはしてないので、定期で走らせたいならそういうのはよろしく頼みます。

## 学んだこと

- os.Exit()するとdeferが死ぬ。returnを使え。
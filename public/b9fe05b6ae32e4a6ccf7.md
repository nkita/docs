---
title: タグで管理するToDoアプリが完成するまで
tags:
  - TypeScript
  - 個人開発
  - Todoアプリ
  - Next.js
  - chakra-ui
private: false
updated_at: '2023-05-27T22:42:19+09:00'
id: b9fe05b6ae32e4a6ccf7
organization_url_name: null
slide: false
ignorePublish: false
---
# はじめに
こんにちわ、nkitaoと申します。
35歳にして、急に個人開発に目覚めた漫画、ゲーム好きの社内SEです。
この年齢で今から個人開発？？なんて、今さら感がすごくあるのですが、趣味や何かに没頭することに年齢なんて関係ないよね！

個人開発歴は１年未満のほぼ素人ですが、個人開発したもの、していくものを綴っていきたいと思います！

# 作っているもの
[TagToDo（モック）](https://nkita.github.io/todo-tutorial/mock)
![tagtodo_mock.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/237628/556602a4-cade-144c-4bea-869a1d5817ef.png)
github pagesで開発中のものを公開しています。

## 何ができるのか
* ToDoをTagと一緒に管理するアプリ
* URLさえ知っていればどこでも同じToDoを開ける（未実装、これから）
* スマホ対応のデザイン（未実装、これから）

## なぜ作ろうと思ったのか
前回[ガントチャートツール](https://qiita.com/nkitao/items/cd70fc8f0fbc0983ec69)を作成してみてすごく楽しかったので、別のツールも作りたいと思った。
ToDoアプリも巷にたくさんあふれているけど、Tagと一緒に使いやすいToDoを見つけられなかったので作ってみようと思った！
とにかくじゃんじゃんToDoをつっこんであとからTagで整理できたらいいなぁ。ってね！

あと、Next.jsやchakra-uiも使ってみたいという思いもありました。


## 開発概要
### 言語
* TypeScript 
### ライブラリ
* [Next.js](https://github.com/rsuite/rsuite)
* [Chakra-UI](https://github.com/MaTeMaTuK/gantt-task-react)
大変お世話になったライブラリたちです。
超リスペクトです。

## 最後に

まずはモックを作ってイメージつかんでから、次のステップに進もうと思っていたら
なんだか、満足してしまった。
困った。


Next.js13.4でapp directoryが安定版になったー！
さあ、今のモックも作り直そうかな！！楽しみ！！orz

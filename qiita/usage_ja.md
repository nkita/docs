# コミットメッセージ作成ツールとは？  
コミットメッセージ作成ツールは、コミットメッセージの作成を支援するためのツールです。
コミットメッセージを作成する際や過去のコミットログを振り返る際に、次のような問題に直面したことはありませんか？

* メッセージが一貫しておらずわかりにくい
* プロジェクトごとに異なるフォーマットがある
* スコープの名称に揺れがある
* 絵文字を使ってメッセージを華やかにしたい

コミットメッセージ作成ツールは、これらの課題を解決するために開発しました。

1. Webベースで簡単に利用可能
2. インストール不要
3. 過去の入力内容を記憶し、再利用できる機能を搭載

なお、本ツールではより利用しやすいよう、ログインは不要であり、設定情報はすべてブラウザ内に保存される設計になっています。

# 使い方
コミットメッセージ作成ツールにはコミットメッセージ作成モードとカスタマイズモードの２つのモードがあります。

## ⚡コミットメッセージ作成モード
テンプレートに沿ったフォーマットでコミットメッセージを作成することができます。
使用する場合は、画面左側の入力フォームへ該当の情報を入力するだけで、画面左側の出力エリアに整形されたコミットメッセージが表示されます。

テンプレートは右上の「テンプレートを選択」から選択することが可能ですし、新規オリジナルのテンプレートを作成することも可能です。

## ⚡カスタマイズモード
現状は下記の項目がカスタマイズ可能です。  

### タイトル
タイトルではテンプレートの名称を変更することができます。たとえば、プロジェクトごとにコミットメッセージのフォーマットが異なる場合、プロジェクト名をタイトルに含めることで、わかりやすくなります。

### 説明文
テンプレートの説明文を変更することが可能です。  
説明文にはMarkdown形式に対応しているため、見出しやリンク等、わかりやすい記述で表現することが可能です。  
テンプレートを利用するにあたっての注意点などあればこちらに記述ください。

### 入力フォーム
入力フォームは、コミットメッセージ作成モードでコミットメッセージの作成するための入力フォームになり、下記の項目が対象になります。
* 種別
* 要約
* スコープ
* 本文
* フッター

入力フォームのカスタマイズでは項目の形態を変更することが可能です。  
デフォルトテンプレートにおける形態に関する説明は下記をご覧ください。
<br />
| 種別| 説明| 該当フォーム|  
| :---- | :---- | :---- |  
| １行テキスト| 要約のような短くわかりやすいメッセージを入力するフォームです。　| 要約|
| 複数行テキスト| メッセージの詳細な内容を入力するフォームです。| 本文、フッター|
| 固定値ドロップダウンテキスト| あらかじめ指定された入力内容を選択するフォームです。<br/>各オプションの意味は説明文に記載されています。| 種別|
| 動的ドロップダウン| 入力内容を自動的に保存することが可能であり、<br/>次回コミットメッセージ作成時に記入の揺れを軽減することが可能です。| スコープ|  
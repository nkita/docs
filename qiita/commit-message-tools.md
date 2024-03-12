
[![スクリーンショット 2024-03-12 14.21.07.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/237628/5a897259-54d1-d321-19f9-11ad04d7181c.png)](https://shiba-tools.dev/)

はじめまして、ShibaToolsというWebオンラインツールを趣味で開発・運営しているnkitaoといいます。

タイトルに記載のとおり、ちゃんとしたコミットメッセージを書くために作ったものと、その経緯について書いています。

## なぜ？

個人開発を１年半ほどやってみて、[プライベートなガントチャート](https://qiita.com/nkitao/items/cd70fc8f0fbc0983ec69)や[ChatGPTで英語を学習](https://qiita.com/nkitao/items/a5f11b75c9033b75d34b)というツールを作ってきましたが、プライベートな事情もあり一旦個人開発から離れていました。

なんやかんやあり、もろもろ落ち着いてきたので、個人開発再開するぞ〜！と思い、前回のプロジェクトの修正・改修した内容（コミットメッセージ）を振り返ってみたところ・・・
![スクリーンショット 2024-03-12 13.30.55.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/237628/4dd8f7f2-6889-8350-9ca1-ca49b4ec5bcd.png)

と、まぁ、載せるか躊躇するレベルの酷さで、いかに適当にログを残してたんだなぁと反省しました。
そこでこの機会にちゃんとコミットメッセージを残そうと思い至りました。

## コミットメッセージのフォーマットが必要なの？
[Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/)では、仕様定義することで、自動化ツールの導入が容易になるとの記述がありました。
>Conventional Commits の仕様はコミットメッセージのための軽量の規約です。 明示的なコミット履歴を作成するための簡単なルールを提供します。この規則に従うことで自動化ツールの導入を簡単にします。

私は使ったことはないのですが[About](https://www.conventionalcommits.org/en/about/)ページの「Tooling for Conventional Commits」に、関連するツールの一覧がありました、
おそらく、バージョン管理やリリースを自動的に行うためのツールであったり、過去のログを分析するためのツール？のようなものだと思います。
確かにプロジェクトが大きくなり、本格的にタグ付けやバージョン管理し始めると重要になってくると思います。


また、Conventional Commitsは[Angular - Commit Message Format](https://github.com/angular/angular/blob/main/CONTRIBUTING.md#commit-message-header)からインスパイアされたらしく、また、Angularは[AngularJS](https://docs.google.com/document/d/1QrDFcIiPjSLDn3EL15IJygNPiHORgU1_OOAqWjiDU5Y/edit#heading=h.uyo6cb12dt6w)からインスパイアされたみたいです。

Angular、AngularJSのガイドラインを見ると、主にフォーマットを定義する理由としては、
過去の履歴を追いやすくし、[CHANGELOG](https://github.com/angular/angular/blob/22b96b96902e1a42ee8c5e807720424abad3082a/CHANGELOG.md)を自動生成するために利用されているとの記述がありました。
Angularリポジトリでは、CHANGELOGの情報がそのままリポジトリのリリースに直接紐づいているため、機械的に生成するためにも特に厳密にフォーマットが定義されているのだなと感じました。

![qiita - article.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/237628/65dd3359-e2c1-9f5a-d34b-d6b090e200ef.png)

また、過去の履歴を追いやすくすることで、メンテナンス性は確実にあがりますし、過去同様な修正があった場合や、コントリビューターがプロジェクト参入後に状況を把握しやすいという観点から、生産性の向上にも寄与すると思います。

また、QittaやZennに投稿されている記事にもいくつか書かれているとおり、コミットメッセージを統一することでのメリットは十分あるのだとわかりました。

↓↓参考にさせていただいた記事 :bow: 

https://qiita.com/pasca-l/items/40bb1d4e9afa3033db2e

https://zenn.dev/itosho/articles/git-commit-message-2023


## 実現したいこと
コミットメッセージのフォーマットのメリットと必要性については十分理解できましたところで、早速フォーマットに
したがって書いていたのですが、まぁ覚えるのに時間がかかりますし、ツールを導入してみたところ
概ね便利なのですが、プロジェクトごとにもう少し具体的な種別やスコープにカスタマイズしようとすると、すこし管理が面倒に感じてしまい、鳥頭な私にとっては一つのツールを導入し、管理や維持していく手間をできるだけ避けたいと思いました。

また、下記記事に記載されているとおり、コミットログが絵文字で彩られていると幸せな感じがするので、自分のプロジェクトには絵文字を使いたいなと思いました。

https://qiita.com/SabaCrevette/items/5a51e86c55c459c77d8e


前置きが長くなりましたが、自分なりにちゃんとしたコミットメッセージを残すための要件をいろいろまとめると、以下のような本当に自分だけにマッチしそうな条件になってしまったので、自分でツールを作ることに決めました。
* フォーマットされたコミットメッセージが作成できること
* インストール不要であること
※だけど、カスタマイズもちゃんとできること
* 過去の入力情報を再利用できること（スコープとかで使いたい）
* 絵文字のメッセージを残したい
* 絵文字使いたいけど、毎回コピペするのは避けたい


## 作ったもの
そして出来上がったのがこちらです。
[コミットメッセージ作成ツール](https://shiba-tools.dev/tools/commit-support-original)
[![スクリーンショット 2024-03-09 21.44.57.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/237628/ab0e1376-5ac4-9cf2-e825-aa70d1988af7.png)](https://shiba-tools.dev/tools/commit-support-original)


## 使い方
使い方は非常にシンプルで、種別、要約、スコープ、本文、フッターにコミットメッセージを記入するだけで、右側のエリアにフォーマットされたコミットメッセージが表示されます。
必要であれば`git commit -m`コマンドも一緒にコピーできます。

## こだわったところ
UIや各機能はどれもこだわったところなんですが、特に以下の部分こだわりました。
* **カスタマイズ機能**
プロジェクトごとに自由にテンプレートをカスタマイズ＆制限なく作成することができます。
プロジェクトによって種別（feat、fix、build等）で利用するもの利用しないものが変わってくるかと思いますが、プロジェクトに合わせて自由に追加・削除ができます。

* **保存できるドロップダウン** 
スコープの項目の動的ドロップダウン（Dynamic-Dropdown）は、過去に入力した情報を自動的に保存してくれる項目になります。
私だけじゃないと思いたいのですが、以前入力した情報を再利用したいケースがありませんか？
以前どんな記述をしたのか思い出すのにログを漁ってるうちに諦めて、それっぽい命名をしたところ、やっぱり表記揺れがあり悲しくなったことは少なくないです。

* **キーボードファースト**
Webサービスになるので、どうしてもブラウザを開いてアクセスという手間かかってしまいます。
この手間はどうしようもないですが、少なくともメッセージを作成する上でマウスでカチカチしなくてもキーボードから手を離さずに
コミットメッセージを作成できるように心がけました。

## 苦労したこと
コミットメッセージのフォーマットを作成するにあたり、一般的または汎用的なフォーマットを知る必要がありました。
* [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0-beta.4/)
* [Angular - Commit Message Format](https://github.com/angular/angular/blob/68a6a07/CONTRIBUTING.md#commit)
* [AngularJS Git Commit Message Conventions](https://docs.google.com/document/d/1QrDFcIiPjSLDn3EL15IJygNPiHORgU1_OOAqWjiDU5Y/edit#heading=h.uyo6cb12dt6w)
* [Semantic Commit Messages](https://gist.github.com/joshbuchea/6f47e86d2510bce28f8e7f42ae84c716)

上記仕様を読み、本ツールで提供するデフォルトのフォーマットはできるだけ汎用的なものにいようとこころがけました。
例えば、[AngularJS Git Commit Message Conventions](https://docs.google.com/document/d/1QrDFcIiPjSLDn3EL15IJygNPiHORgU1_OOAqWjiDU5Y/edit#heading=h.uyo6cb12dt6w)に以下のように記載されているとおり
> Any line of the commit message cannot be longer 100 characters! This allows the message to be easier to read on github as well as in various git tools.

１行あたりの文字数を100文字以内に収めたほうが、ツールを介してログを確認する際に便利となるケースが多いため、本ツールではその旨のメッセージを表示します。

:::note
100文字を超えた時点メッセージは表示されますが、100文字以上のメッセージを作成することもできますし、コピーすることも可能です。あくまで補足情報として表示されます。
:::

なお本ツールの作成に際して、Angularのコミットメッセージフォーマット用のツールも作成しているので、お時間あればこちらも見ていただけると嬉しいです。

https://shiba-tools.dev/tools/commit-support-angular


## 最後に
早速上記ツールを使ってコミットメッセージを作成するように心掛けたあと、下記のように個人的にはテンションがあがるコミットメッセージを作成することができました。
![スクリーンショット 2024-03-12 15.00.37.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/237628/2a0069f6-31cb-d17c-5510-7439c4646a3d.png)

コミットメッセージのフォーマットについては、ある程度慣れてくるとテンプレートがなくてもある程度規則正しい形で記述することができるようになると思いますが、git初学者や私と同じような考えを持った人には有益なツールになるんじゃないかなと
思っています。


もし良かったらフィードバックいただけると泣いて喜びます！
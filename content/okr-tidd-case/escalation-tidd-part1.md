---
title: "エスカレーション対応のチケット駆動開発 前編"
date: 2020-12-16T13:11:26+09:00
---

[#ssmjp Advent Calendar 2020](https://adventar.org/calendars/5210) 16日目の記事です。

お話する時間は無かったので、
「チケット駆動開発がまわりはじめるまでの取り組み」では、
「誰が」「何をするか」「何をしているか」「どこまで出来ているか」が
少しずつチケットとして見えるようになってきたとだけ書きました。

今日は、「チームにくるエスカレーション」が、
どのようなモチベーションではじまり、
どのような状況を観測し、どのような戦略を考えたのかについて書きました。
書いていると結構なボリュームになったので、前編、中編、後編に分けました。

チケット駆動開発がまわりはじめるまでの取り組み

https://speakerdeck.com/zinrai/okr-tidd-case

## モチーベーション

「 [チケット駆動開発をチームメンバーに展開する 前編](/okr-tidd-case/introduce-tidd-team-part1) 」
「 [チケット駆動開発をチームメンバーに展開する 後編](/okr-tidd-case/introduce-tidd-team-part2) 」
の仕組みは、日々の開発業務を親子の構造でチケット管理する目的で利用していました。
「自身の業務をチケット化することに慣れる」のタイミングでは、
「チケットを作ることに慣れてもらいたい」に注力していました。

「自身の業務をチケット化することに慣れる」での週次の棚卸しの中で、
「問い合わせやアラート対応のようなものをチケット管理できていない」というコメントが参加者から上がりました。

何も考えていなかったわけではなく、
「チケット駆動開発」を推進しているのは自分一人で、
自分一人で一度に出来ることには限界があるため、
一つずつ確実に進めていきたいという思いがありました。

「自身の業務をチケット化することに慣れる」では、
これから「チケット駆動開発」がどのように進んでいくかは不確実であったため、
問い合せやアラート対応のようなものを「チケット駆動開発」するのは後回しにすると決めていました。

「自身の業務をチケット化することに慣れる」での週次の棚卸しの中で、
問い合せやアラート対応への「チケット駆動開発」の機運が高まっていることを感じ取り、
区切りとしていた三ヶ月のタイミングでは、
参加者の反応から「チケット駆動開発」を他の用途にも利用していけそうな感触がありました。

「チケットをベースにチームメンバーと協力しながら作業を進める」のタイミングからは、
同時進行で、「問い合せやアラート対応をチケット駆動開発する」を進めていくことを決めました。

## 現状の整理

「問い合せやアラート対応をチケット駆動開発していきましょう」
だけでは「チケット駆動開発」には乗っていきません。
戦略をたてる必要があります。
戦略をたてるためには現状を整理しておく必要があります。
チームミーティングやチームメンバーを観察していた中で、
問い合せやアラート対応の現状がどうであったかについて整理しました。

### 窓口が沢山ある

前職にて、所属していた部では窓口は一つに集約されており、
Redmine に「エスカレーション」チケットを起票することで、
他部署とのやりとりを行う仕組みとなっていました。
「エスカレーション」のチケットが起票されているプロジェクトを参照するだけで、
どのようなエスカレーションが来ているのか、自分が担当しているのはどれかを確認できていました。

現職では、チームミーティングで聞こえてくる内容から、
Slack チャンネル、 メーリングリスト、
別チームからの依頼が起票されるシステムなど様々な箇所が、
問合せやアラート対応の窓口になってそうであることを感じました。

メンバーごとに知っている窓口が異なってそうで、
全容を知る人は誰もいないのではないのかと思いました。

### Slack DM がくる

最悪です。
誰も状況を観測できません。
個人商店を観測しました。

### 能動的に動いている

沢山ある窓口から来たものを能動的にチームメンバーが取っていくというスタイルでした。

### 対応状況がわからない

チームメンバーによって対応のリアクションがあったりなかったり、
状況をコメントしてくれていたりそうでなかったりとまちまちな状態で、
チームミーティングで聞くまで対応の状況をがよくわからないということが頻発していました。

能動的に動いていくスタイルのため、リアクションをしていないと、
対応が被っていても気付かずに同じ問い合せやアラート対応進めてしまうことがよく起きていました。
そのため、「これ取っていいのかな、対応被ってないかな」という気を回している状況を観測しました。

### 対応状況の確認が大変

対応状況を一覧できるような仕組みは無く、
状況を確認したければ沢山ある窓口を一つ一つ確認していく必要がありました。
確認したとしても、メンバーによって状況を書いているかはまちまちなので、
情報が得られるとは限らない状況でした。

### ナレッジがほとんど無い

検証結果が記録として残っておらず、
同じ検証を何度もやってしまっていたということをメンバーの一人から聞きました。
対応内容を記録するかはチームメンバーの意識に依存しており、
ナレッジになっているものはほとんど無い状態でした。
ナレッジになっていないので、「その人しか対応できない」というものが沢山ある状態でした。

## 戦略

問い合せやアラート対応の現状を整理した結果から、
どのように「チケット駆動開発」を導入をしていくかの戦略を立てました。

### 小さくはじめる

「チケットをベースにチームメンバーと協力しながら作業を進める」と同時進行になります。
「問い合せやアラート対応のチケット駆動開発」がどう進んでいくか不確実です。
メインのチケット駆動開発に注力したいので、
不確実なチケット駆動開発のほうは、
不確実だけれどもコントロールできそうな範囲で導入を進めていきたいと考えました。

「自身の業務をチケット化することに慣れる」での週次の棚卸しの中で、
声を上げてくれたメンバーが一番課題感を持っていて、
モチベーションを高く持って取り組んでもらえるであろうと考えました。

最初のメンバーとしては、
「 [チケット駆動開発をチームメンバーに展開する 前編](/okr-tidd-case/introduce-tidd-team-part1) 」より、
声を上げてくれた B さん、 D さんを巻き込むことに決めました。

### 運用ルールはフィードバックを受けながら調整する

運用ルールが最初からキッチリと決まるとは思っていません。
自分が観測した状況を反映した運用ルールを作成し、
参加メンバーに運用してもらい、
週次でその結果をフィードバックしてもらうことで、
運用ルールをチームに合う形にしていくことを決めました。

### 参加メンバーを増やすタイミング

参加しているメンバーから運用ルールの
フィードバックが無くなったタイミングで、
新たなメンバーを追加することを決めました。
フィードバックが無くなったということは、
参加しているメンバーの中では、
用意している運用ルールが違和感なくまわりはじめたのだろうと考えました。

### 窓口を洗い出す

窓口が沢山ありそうだなとは感じましたが、その全容はわかっていません。
チームメンバーごとに把握している窓口が違いそうであることは感じています。
巻き込んだメンバーが知っている範囲での窓口を洗い出していき、
最終的にチームメンバー全員を巻き込めたら、窓口が全て洗い出せるのではないかと考えました。

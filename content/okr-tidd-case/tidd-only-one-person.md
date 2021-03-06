---
title: "一人チケット駆動開発"
date: 2020-12-12T10:08:57+09:00
---

[#ssmjp Advent Calendar 2020](https://adventar.org/calendars/5210) 12日目の記事です。

「チケット駆動開発」として見せられるものがなかったので、
まずは「一人でチケット駆動開発する」は、 Redmine Japan 2020 でお話し、
[「チケット駆動開発」導入の戦略](/okr-tidd-case/strategy-tidd) にも書きました。

今日は、お話できなかった具体的にどのように一人チケット駆動開発していたのかについてのかについて書きました。

チケット駆動開発がまわりはじめるまでの取り組み

https://speakerdeck.com/zinrai/okr-tidd-case

## 手元に Redmine を構築した

「チケット駆動開発」に自分がどれだけ助けれら、
どれだけ強力なツールであるかを私は知っています。
Redmine や「チケット駆動開発」がないから、
ここではやらないという考えは一切ありません。
Redmine と「チケット駆動開発」がないならば自分で用意するまでです。

入社初日のチームミーティングにて、
Redmine も「チケット駆動開発」がないことはわかりました。
事前に手配してもらっていたセカンダリのノートパソコンを
入社初日に速攻で Debian GNU/Linux ( sid ) に入れ替えました。
入社初日は週末だったので、
次の週のはじめに Debian に入れ替えたノートパソコンに Redmine をセットアップし、
「チケット駆動開発」を開始しました。
これで「やること」「決めること」を覚えなくてよい環境が用意でき、脳への負荷が減りました。

## Redmine を立てられる環境を探し、構築した

手元の環境で Redmine を動かすのは一時的な対応で、
社内からアクセスできる場所に Redmine をセットアップして、
自分の動きを誰からでも見える状態することを次の目標としていました。
入社したばかりで、どこにどのようなリソースがあって、
どのように使えばよいかが全然わかりません。

まずはチームで使われているツールをキャッチアップしていけば、
サーバーを立てられる場所に辿り着くだろうと考え、
社内のドキュメントやコードを「チケット駆動開発」しながらインプットしていくことにしました。
インプットしている中で Terraform のコードを見付けました。
Terraform Configuration を書き Redmine 用のサーバーを払出し、
Ansible Playbook を書いて適用し、社内から誰でも参照できる Redmine を用意することができました。

なぜそうしてしまったのか思い出せませんが、
手元の Redmine のデータをマイグレーションせずに、
セットアップした Redmine を使いはじめてしまいました。
なぜ手元の Redmine のデータをここにマイグレーションしなかったのかと今でも悔やんでいます。
次に同じような状況になった場合は、一度冷静になってマイグレーションしようと思っています。

## チケット駆動開発しているものを見せながら状況を説明する

私は「チケット駆動開発」がよいものであるということを信じています。
だた、それを誰の目にも触れないところでやってしまっては、気にも留めてもらえません。
このようなやり方があるということを自ら発信していかなければ、誰かの目には留まりません。
手元の Redmine で「チケット駆動開発」していては、
やり方が気になった人が、私のやっていることを見ることができないので、
早々に社内から誰でもアクセスできる環境に Redmine を構築しました。

いま何を進めているのか、どこまで何が出来ていて、
どの地点で、何が残っているのかなどの状況を聞かれたときは、
必ず「チケット駆動開発」している Redmine を見せながら説明するようにしていました。
今までずっとこのような動きをしていたので、やることにストレスはありません。
むしろ Redmine なしで状況を説明するほうが自分への負荷が高くてストレスです。

全ては、自分への負荷を減らすためにやっていることで、
誰かが気にかけてくれたらもうけもん、くらいの気持ちでやっていました。

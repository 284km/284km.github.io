---
title: Ready for Apple Developer
date: 2014-04-03 16:24 JST
tags: ios
---

タイトルのとおり、 Apple Developer 登録について一連の流れをここに残す。

1. apple id をとる
2. developer 登録する ( 8400 円ほど)
  - お金払ってから少し (1 day ほど) 待つことになる。メールが来るまで待つ。
3. key を作って登録する。app id を登録する。
  - [こちら](http://r-dimension.xsrv.jp/classes_j/ios_test/)が非常に分かり易かった。
4. device 登録する。
  - lightning ケーブルで使用するデバイスを繋いで、xcode の Organizer で Use For Development ボタン。
5. provisioning profiles
  - xcode の Organizer から 使用 device の Provisioning Profiles に Add する。
6. 実機で実行
  - これで実機で起動することができる。xcode で登録した device を選択して実行 !!
  - はじめて動かした時には少しくらい感動するかもしれない。

- その他メモ。

> ここで重要な作業があります。App IDはXCodeで作成されたプロジェクトの「Bundle Identifier」と同じでなければなりません。
openFrameworksのiOSプロジェクトの場合は、プロジェクトの中に「ofxiphone-info.plist」というファイルがあるので、これを選択します。「${PRODUCT_NAME:identifier}」と書かれているので、これにApp IDを先頭に追加します。「*」はつけません。
例：jp.xsrv.r-dimension.${PRODUCT_NAME:identifier}


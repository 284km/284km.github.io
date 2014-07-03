---
title: Android Studio On Windows
date: 2014-07-03 09:07
tags: android
---

Windows 環境で Android Studio を使う機会が訪れたためメモを作業ログをとってみよう。

まず、サイトから Android Studio をダウンロードしてきて .exe を実行しインストール。特に変わったことはない。

次に Android Studio の起動に失敗した。java がないと。

Oracle サイトから java SE を入れる。

JAVA_HOME を PATH に加えても Android Studio の起動に失敗する。

ググると、どうやら以下も PATH をとおす必要があるらしい。

- Android/android-studio/tools
- Android/android-studio/platform-tools

あーやっと動いた。この後小一時間はまってしまったが、
java 8 では動かず java 7 jdk にしたら
とりあえず Android Studio が起動した。


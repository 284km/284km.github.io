---
title: Android Studio on Xubuntu
date: 2014-07-03 10:56
tags: android
---

サイトからダウンロードして tar -zxvf する。今回は home へ。

java が必要なのでなければいれる。

Oracle JAVA でなければいけない模様。これではだめ。

    sudo apt-get install openjdk-7-jdk

こっちいれること

    sudo add-apt-repository ppa:webupd8team/java
    sudo apt-get update
    sudo apt-get install oracle-java7-installer

なお、ここにはいる。

/usr/lib/jvm/java-7-oracle/

android studio の起動。うまくいった。

~/android-studio/bin/studio.sh


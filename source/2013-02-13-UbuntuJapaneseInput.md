---
title: Ubuntuで日本語入力する(起動時にiBusを自動で上げるやり方)
date: 2013-02-13 07:50
tags: ubuntu, ibus
---

僕はUbuntuを英語表示で使っていますが、日本語を入力したい時だってあります。
そんな時インプットメソッドのiBusが起動していないと、
あれ、あれ、日本語にならないぞ。あ、iBusか。とかなります。
面倒なので自動起動させたいdesu。

homeに.xprofileを作成して、4行書きましょう。

    % vi ~/.xprofile
    export XMODIFIERS=”@im=ibus”
    export GTK_IM_MODULE=”ibus”
    export QT_IM_MODULE=”xim”
    ibus-daemon -d -x

再起動すると、きっとiBusも起動するはず。


---
title: Need rb-readline On Xubuntu
date: 2014-07-07 14:17
tags: ruby, ubuntu
---

Xubuntu 上で とある Rails のアプリケーション でも動かそうとしたら bundle exec rails s しても動かなくて、

rb-readline を install するか、
readline オプションつきで ruby をインストールせよ。という感じのメッセージが出ていた。

ちょっと入れなおすほど時間かけたくなかったので、 Gemfile に gem 'rb-readline' を追加して bundle install したら rails s できるようになった。



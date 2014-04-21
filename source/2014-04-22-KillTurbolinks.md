---
title: Rails4 Turbolinks を切る
date: 2014-04-22 06:22
tags: rails, turbolinks
---

人類には早過ぎると思うし、とても僕が turbolinks を一番うまく扱える気はしないし、ましてや俺が turbolinks だなんて言えやしないのでタイトルの通り turbolinks は切る方向で。暫くは。

### というわけで手順

- rails new で bundle install はスキップしておく

    rails new hoge --skip-bundle

- Gemfile から `gem 'turbolinks'` をはずす

- アセットパイプラインのマニフェストから turbolinks を削除

    //= require turbolinks

- application.html.erb から `"data-turbolinks-track" => true` を削除

そして改めて bundle install する。

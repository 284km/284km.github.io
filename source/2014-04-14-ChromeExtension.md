---
title: Chrome Extension
date: 2014-04-14 16:13
tags: chrome
---

## Chrome Extension の種類について

manifest.json に書くことになるが、三種類ある。以下はそれぞれの簡単な説明。

### app

`chrome://apps/` に並ぶタイプのもの。

### browser_action

アドレスバーの右側にアイコン表示するタイプのもの。

### page_action

アイコン表示したくないような場合にはこちらを使う。

- おまけ

とても小さなものならすごく簡単に作れる。Chrome Extension を作ったことが無い人でも 10 分程度でどんな感じか分かると思う。
サンプルとして app のタイプのものが以下にある。

どんな感じかさくっと体験してみたい人は、これを clone して、chrome の設定から Extensions の Developer mode のチェックを ON して、clone した extension を読み込ませてみるとよいと思う。
すると `chrome://apps/` に並ぶので、クリックするとサンプルページが表示されるはずだ。

https://github.com/284km/chrome-extension-minimal



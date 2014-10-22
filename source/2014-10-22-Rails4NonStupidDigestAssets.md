---
title: Rails4 の assets precompile に関する注意点と現時点での対応方法
date: 2014-10-22 10:18
tags: rails, rails4
---

身近なところで、よく困っているところを目にする問題なので、ちょっとまとめておく。

まず問題となっているのは、rails4 にしたら画像が表示されない! みたいな事象。

それは、Rails4 からは digest 無しの js, css, image は作成しない仕様となった為。
以下で詳しく説明してくれている。

http://qiita.com/wadako111/items/03bc00d914e62243a511

ここでは以下の対処方法を提示してくれている。

- asset_path関数, image-url関数を使う

- public/assets 以下に画像を直接置く

- public/images 以下に画像を置く

個人的には以下の jnchito さん記事の non-stupid-digest-assets gemを導入する。
で一先ず対応しておくのがよいと思っている。

http://qiita.com/jnchito/items/07f2e3ca29f9881b83d6

issues も相当長くなっている。

https://github.com/rails/sprockets-rails/issues/49

以下のメッセージを最後に lock されているので、今後何らかの変更があるのかもしれない。と思っている。
そういう訳で、自分の場合は [alexspeller/non-stupid-digest-assets](https://github.com/alexspeller/non-stupid-digest-assets) を使ってとりあえず様子を見ておくことが、一番よいのではないかという考えをしています。

> Thank you. I locked this conversation. We already have enough information to think about this issue and in fact we are going to handle it in some way (we already did some improvements on master branch to alleviate the pain). If we think we need more feedback from the community I'll reopen the thread.



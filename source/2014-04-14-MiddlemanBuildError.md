---
title: Middleman Build Error
date: 2014-04-14 10:45 JST
tags: middleman
---

今日記事を追加しようとしたら、Travis-CI から通知がきて middleman のビルドエラーが起きていた。
はて、いつもどおりに追加したはずだが。

middleman-blog を追ってみたところ、どうやら日付の指定 (ファイル名につけるやつ) が悪いらしい。コードを見た限りでは、現在日より未来だからっぽい。

それにしても日付は今までどおり当日を入力しており未来日ということもなかろう。 config.rb を眺めてみるとタイムゾーンを指定していないことに気づく。デフォルトで UTC とかになるのだろうか。そうだとすると、未来日だという主張も頷ける。というわけで `Time.zone = "Tokyo"` を追加して push したところ今度は別のエラーだ。日付の問題はやはりタイムゾーンの問題だったということのようだ。

残りのエラーは、いくつかのファイルが対象となった。すべて昔作った動作確認テスト用の article だ。拡張子が `.html.markdown` だったりがいけなかったのか、よく覚えていないが不要なファイルであったため git rm したところビルドが通った。

全部直ったが、意識しておくこととしてはたまに挙動がかわることがあるということ。middleman がわの。だから早くブログシステム移行したい。とかずっと言い続けているけれど結局 middleman の投資対効果はなかなかのものなのでそこに依存している。いや悪くはないんですが。middleman。コードも見れば分かるものだったし暫くは問題ないのではないか。


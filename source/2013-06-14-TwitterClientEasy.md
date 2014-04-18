---
title: Dead Simple twitter client in Terminal
date: 2013-06-14 10:13
tags: twitter, ruby
---

よくあるターミナルでやるやつです。
アプリケーション登録する必要があります。

引数をつぶやきます。引数無しでタイムライン表示します。細かいことは考えません。
たとえばこんな感じに使います。 twt.rb というファイル名で以下のコードを保存してruby twt.rb hey! I am tweeting!! とつぶやいたり、ruby twt.rb でタイムライン表示します。

    require 'twitter'↲
    @client = Twitter::Client.new(↲
      consumer_key: "xxx",↲
      consumer_secret: "xxx",↲
      oauth_token: "xxx",↲
      oauth_token_secret: "xxx"↲
    )↲
    if ARGV[0]↲
      @client.update(ARGV.join(" "))↲
      puts "updated:" + ARGV.join(" ")↲
    else↲
      @client.home_timeline.each do |tl|↲
        puts "#{tl.from_user}: #{tl.created_at}"↲
        puts " -> #{tl.text}"↲
      end↲
    end↲

というもの


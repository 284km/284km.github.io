---
title: Twitter via tweet button
date: 2013-12-04 20:06
tags: twitter
---

ボタンを押してツイートするだけの用途です。

事前に書きたいことをメモしたい時もあるので、textarea をボタン下に配置しています。

`data-text="xxx"` でボタン押下後のデフォルトメッセージを設定しておけます。

`data-hashtag="xxx"` で同じくボタン押下後のデフォルトハッシュタグを設定しておけます。

tweet_button.html

    <!DOCTYPE html>
    <html>
    <head>
    <title>tweet_button</title>
    </head>
    <body>
    <a href="https://twitter.com/share" class="twitter-share-button" data-count="none" data-text="write here" data-hashtags="now_working">tweet</a>
    <br><textarea cols=40 rows=5></textarea>
    <script>
    !function(d,s,id){var js,fjs=d.getElementsByTagName(s)[0];if(!d.getElementById(id)){js=d.createElement(s);js.id=id;js.src="https://platform.twitter.com/widgets.js";fjs.parentNode.insertBefore(js,fjs);}}(document,"script","twitter-wjs");
    </script>
    </body>
    </html>



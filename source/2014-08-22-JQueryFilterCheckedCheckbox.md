---
title: JQuery Filter Checked CheckBox
date: 2014-08-22 17:24
tags: jquery, javascript
---

久々に jquery を書いたら css セレクタの書き方とかかなり忘れていて残念すぎる気持ちになった。

チェックされたチェックボックスだけ数えるところで手が止まったのでここに残すことにした。

こんな感じにやった。 id 指定していなくて元のままやる方向性のようでこうしている。

    tableRowCount = $('.table-foobar tr td.delete input[type="checkbox"]').filter(":checked").length

css セレクタも英単語も jquery も忘れていくもののようで、定期的に振り返ることが必要そう。


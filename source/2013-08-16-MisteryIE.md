---
title: IE の不思議 その１ getElementsByName
date: 2013-08-16 10:29
tags: ie, javascript
---

なぜ IE だけこんな挙動なのか?
getElementsByName() で、IE だけ拾えてないのなんでだろうと思っていたら、name で拾ってくるらしい。
だからこれはダメ

    <input type="file" name="idfile" multiple>

これなら大丈夫

    <input type="file" id="idfile" name="idfile" multiple>

javascript も同様

    var newFile = document.createElement("input");
    newFile.type = "file";
    newFile.setAttribute("name", "idfile");
    newFile.setAttribute("id", "idfile");
    newFile.setAttribute("multiple");
    var div = document.getElementById('iddiv');
    div.appendChild(newFile);



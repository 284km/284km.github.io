---
title: IndexedDB が利用可能か判定する方法
date: 2014-04-20 17:46
tags: javascript , indexeddb
---

これでいいのか?

    if (window.indexedDB || window.webkitIndexedDB || window.mozIndexedDB) {
      console.log("you can use");
    } else {
      console.log("you can't use");
    }


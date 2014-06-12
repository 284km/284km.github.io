---
title: コミット前に間違えて add したファイルを index から戻す方法
date: 2014-06-12 09:39
tags: git
---

Initial commit 前に間違えた場合 head が無いので
git checkout . とか git reset head foobar とかできない。

というような場合はこうして戻す。

    git rm -r --cached foobar


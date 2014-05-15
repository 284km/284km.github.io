---
title: Delete branch on Github
date: 2014-05-15 16:47
tags: github
---

github 上に間違ったブランチを push してしまって消したいとき。

local なら、 git branch -D branchname でいい。

github に push 済みのブランチについては

git push origin :branchname

とする。


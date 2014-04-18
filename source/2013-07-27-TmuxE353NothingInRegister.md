---
title: tmux の vim で E353: Nothing in register とか出る時
date: 2013-07-27 10:21
tags: tmux
---

    brew install reattach-to-user-namespace

して、.tmux.conf に以下を書いて、

> set-option -g default-command "reattach-to-user-namespace -l zsh"

あとは

    tmux kill-server

とかすればOK

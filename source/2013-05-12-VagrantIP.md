---
title: Vagrant 仮想環境にIPを割当てたい
date: 2013-05-12 08:50
tags: vagrant
---

Vagrantfile に追記する

    config.vm.network :private_network, ip: "192.168.50.11"

そして

    vagrant reload

で反映されます。

設定したIPで ssh や MySQL できる様になりました。


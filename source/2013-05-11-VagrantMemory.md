---
title: Vagrant のメモリ割当て
date: 2013-05-11 07:50
tags: vagrant
---

ちょっと貧弱貧弱ゥ!だったのでメモリを2Gに強化した。

Vagrantfile に書く

    config.vm.provider :virtualbox do |vb|
      # Don't boot with headless mode
      # vb.gui = true

      # Use VBoxManage to customize the VM. For example to change memory:
      vb.customize ["modifyvm", :id, "--memory", "2048"]
    end

そして 再起動する。

    vagrant reload

[vagrant reload は稼働しつつ設定ファイルだけ読み込めるわけではないので注意](http://docs-v1.vagrantup.com/v1/docs/getting-started/ports.html)

> calling vagrant reload will apply them without re-importing and re-building everything.



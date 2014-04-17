---
title: Windows7でVagrant - CentOS6.4を使う
date: 2013-05-10 07:50
tags: vagrant, win7
---

必要に迫られて win7 な環境でもやったのでメモ。

まずは VirtualBox と Vagrant をインストールする。

for Windows なやつを設定はデフォルトで入れた。

そうそう [ruby](http://rubyinstaller.org/) も入れておく必要がある。


CentOS は 6.4 がきてたのでこれにした。

    vagrant box add centos http://developer.nrel.gov/downloads/vagrant-boxes/CentOS-6.4-x86_64-v20130309.box

box add でこんなエラーがでた

    /vagrant/embedded/gems/gems/vagrant-1.1.2/lib/vagrant/environment.rb:516:in `expand_path': non-absolute home (ArgumentError)

環境変数 HOME が設定されているのがいけない様なので消してから box add したら上手くいった。

    set HOME=

vagrant up して vagrant ssh すると ssh が無いぞと言われる(ホスト情報が出力されているので teraterm 使って入りました)

    Host: 127.0.0.1
    Port: 2222
    Username: vagrant
    Private key: C:/Users/kazuma/.vagrant.d/insecure_private_key

こんな感じでした。かんたん！


---
title: Vagrant memo
date: 2013-03-26 07:50
tags: vagrant
---

- VirtualBox をインストール

https://www.virtualbox.org/wiki/Downloads

- Vagrant をインストール

http://downloads.vagrantup.com/

- CentOS6.4 をいれてみた

    vagrant box add centos http://developer.nrel.gov/downloads/vagrant-boxes/CentOS-6.4-x86_64-v20130309.box
    vagrant init centos
    vagrant ssh

- 終了は

    vagrant halt


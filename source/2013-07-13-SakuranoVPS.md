---
title: setting of Sakura VPS
date: 2013-07-13 10:16
tags: vps
---

さくらのVPSでの初期設定

yum update

必要なら root の password 変更

passwd

useradd username

passwd username

usermod -G wheel username

vi /etc/pam.d/su

uncomment

auth required pam_wheel.so use_uid

visudo

無い場合は入れる。 yum install sudo

uncomment

%wheel ALL=(ALL) ALL

こっちも uncomment すると pass 入れる必要なくなる。

%wheel ALL=(ALL) NOPASSWD: ALL

re-login as added user

vi ~/.bash_profile

zsh なら .zshrc とかに書く。

PATH=$PATH:$HOME/bin

add the following

PATH=$PATH:/sbin

PATH=$PATH:/usr/sbin

PATH=$PATH:/usr/local/sbin

聞かれる filename pass

ssh-keygen -t rsa -C "your mail address"

そういえば hosts でも書いておく

xxx.xxx.xxx.xxx vps

sftp username@vps

put id_rsa.pub

mkdir ~/.ssh

cd ~/.ssh

: > authorized_keys

cat ~/id_rsa.pub >> ~/.ssh/authorized_keys

rm ~/id_rsa.pub

chmod 700 ~/.ssh

chmod 600 ~/.ssh/authorized_keys

sudo vi /etc/ssh/sshd_config

uncomment

PermitEmptyPasswords no

RhostsRSAAuthentication no

RSAAuthentication yes

PubkeyAuthentication yes

AuthorizedKeysFile .ssh/authorized_keys

PasswordAuthentication yes

PasswordAuthentication no

Port 22

Port 10022

sudo /etc/init.d/sshd restart

ssh vps -i ~/.ssh/id_rsa -lusername -p10022


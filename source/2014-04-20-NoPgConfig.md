---
title: 'gem install error about "No pg_config"'
date: 2014-04-20 07:41
tags: ruby, postgresql
---

こんな具合に gem install pg できなかった。

> checking for pg_config... no
> No pg_config... trying anyway. If building fails, please try again with
>  --with-pg-config=/path/to/pg_config
> checking for libpq-fe.h... no
> Can't find the 'libpq-fe.h header
> *** extconf.rb failed ***
> Could not create Makefile due to some reason, probably lack of necessary
> libraries and/or headers.  Check the mkmf.log file for more details.  You may
> need configuration options.

### 対処法

- Debian

    sudo aptitude install libpq-dev

- Redhat

    sudo yum -y install postgresql-devel

- Mac

    brew install postgresql

### pg_config のパスの指定をしたい場合

    gem install pg --with-pg-config=/usr/local/bin/pg_config

- bundle install の場合

    bundle config build.pg --with-pg-config=/usr/local/bin/pg_config
    bundle install


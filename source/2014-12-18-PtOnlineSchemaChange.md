---
title: pt-online-schema-change
tags: mysql, pt-pnline-schema-change
date: 2014-12-18 15:02
---

mysql 5.5 以下でも、online でスキーマ変更とかを可能とするあれだ。

http://www.percona.com/downloads/percona-toolkit/2.2.12/tarball/percona-toolkit-2.2.12.tar.gz

tar ball を持ってきて解凍して、中にある pt-online-schema-change だけ持ってきて使った。

例えばこんな風に使う。

dry-run

    ./pt-online-schema-change h=localhost,u=username,D=databasename,t=tablename --alter "add index index_name(columnname)" --set-vars innodb_lock_wait_timeout=50 --dry-run

execute

    ./pt-online-schema-change h=localhost,u=username,D=databasename,t=tablename --alter "add index index_name(columnname)" --set-vars innodb_lock_wait_timeout=50 --execute

replication している場合には --nocheck-replication-filters などつける。

    ./pt-online-schema-change h=localhost,u=username,D=databasename,t=tablename --alter "add index index_name(columnname)" --set-vars innodb_lock_wait_timeout=50 --nocheck-replication-filters --execute


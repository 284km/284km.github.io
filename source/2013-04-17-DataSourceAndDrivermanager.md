---
title: DataSource と DriverManager のこと
date: 2013-04-17 07:50
tags: java
---

### Javaのはなしをします2。

http://zetcode.com/tutorials/jeetutorials/datasource/

> DataSource and the DriverManager are the two basic ways to connect to a database in a JEE application. The DriverManager is older facility, DataSource is newer. It is recommended to use the new DataSource facility to connect to databases and other resources. DataSource facility has several advantages over DriverManager facility. Using DataSource increases portability. The DataSource enables connection pooling and distributed transactions, the DriverManager does not allow such techniques. Properties of a DataSource are kept in a configuration file. Any changes to the data source or database drivers are made in the configuration file. In case of a DriverManager, these properties are hard coded in the application and for any changes we must recompile the code.

DataSource と DriverManager という2つのDB接続方法があって

DataSource のが新しくって接続方式として推奨されていて

DataSource 使った方が拡張性たかい



コネクションプーリングできちゃうし分散トランザクション可能

DataSource は設定ファイルで完結する

DB や driver は設定ファイルに定義する



DriverManager だったらアプリにハードコーディングでリコンパイルが必要なところ



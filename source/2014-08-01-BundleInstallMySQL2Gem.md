---
title: bundle install mysql2 gem
date: 2014-08-01 15:18
tags: ruby, rails, mysql
---

mysql2 の gem を bundle install しようと思ったら

    Gem::Installer::ExtensionBuildError: ERROR: Failed to build gem native extension.

とかでた。そんなときは

sudo apt-get install libmysqld-dev

したら bundle install できた。


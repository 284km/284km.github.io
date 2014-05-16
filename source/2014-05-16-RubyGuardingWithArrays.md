---
title: Ruby Guarding with arrays
date: 2014-05-16 12:39
tags: ruby
---

- nil のときエラーになる

    params[:pictures].each do |picture|
      foobar
    end

- ちょいださい

    (params[:pictures] || []).each do |picture|
    end

- こういうのある

    Array(params[:pictures]).each do |picture|
    end

というメモ。


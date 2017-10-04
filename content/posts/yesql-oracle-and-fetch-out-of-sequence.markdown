---
title: "Yesql, Oracle and fetch out of sequence"
date: 2016-10-28T22:08:46+02:00
categories: [Clojure, Yesql, Oracle]
---

If you encounter an ‘ORA-01002: fetch out of sequence’ when running your Yesql functions, make sure you have remembered the exclamation mark after the name of your [insert/update/delete](https://github.com/krisajenkins/yesql#insertupdatedelete-and-more). I have only used Oracle with Yesql, but I expect other databases will give a similar error if you forget this.


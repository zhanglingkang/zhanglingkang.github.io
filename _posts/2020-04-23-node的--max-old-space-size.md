---
layout: post
title: "node的--max-old-space-size参数"
subtitle: ""
date: 2020-04-15
author: "zlk"
catalog: true
tags:
  - max-old-space-size
  - oom
---

### --max-old-space-size 是什么？

存放老生代对象的空间大小

### 是不是设置越大越好？

不是，在 linux 机器上，如果--max-old-space-size 设置过大，而程序本身确实需用占用很大内存，很可能触发系统的 OOM Killer，所以设置一个合适的大小，不会触发系统的 OOM Killer，需要更多内存时，系统会使用虚拟内存。

### 设置过小会怎么样？

设置过小，会触发 node 本身的 OOM

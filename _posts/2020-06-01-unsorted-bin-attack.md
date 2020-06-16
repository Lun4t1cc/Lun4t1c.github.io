---
title: unsorted bin attack
category: 堆
layout: post
---

## # 作用效果

向指定内存写入一个大数。

## # 具体利用

将已被释放的 unsorted chunk 的 bk 指针改为 `目标地址 - 0x10（或 0x8）`，则在取出该 unsorted chunk 时，目标地址就会被一个不可控的大数覆盖。
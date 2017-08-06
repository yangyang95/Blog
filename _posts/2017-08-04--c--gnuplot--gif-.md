---
layout: post
title: "用 C 與 Gnuplot 來建立 gif 動畫"
description: "Example of creating gif with C, gnuplot and ImageMagick(optional)"
date: 2017-08-04
tags: [C, Gnuplot]
author: JerryWeng
comments: true
share: true
---

最近正在讀電機機械基本原理 (Electric Machinery Fundamentals, 4th Edition, Stephen J. Chapman)，看到裡面的 matlab code 就會手癢用 C 改寫看看<br>

昨天，做到一個例題的程式碼是要把馬達中的磁場分布用動畫做呈現<br>
這個用 matlab 可以簡單做到，不過用 C 就沒有那麼簡單，過程中困擾了好久XD<br>

因此在這邊把這個小技巧做個記錄，這個範例會使用到 C 的複數函式庫、popen 函式、sprintf 做格式化，還有 gnuplot 做動畫的技巧。
相當的有趣，做完有種功力大增的感覺 :sunglasses:

廢話不多說，趕快來看結果跟程式碼

<script src="https://gist.github.com/yangyang95/461e388ca10cb2c9776bea26de229431.js"></script>

基本來說，最主要的概念是使用一個 gnuplot 的 script 並不容易產生動畫，因此利用 C 語言來為我們產生 plot script 並執行。再把得到的每一張圖用 ImageMagick 來合成 gif 動畫。


### References
C 的複數函式庫、popen 函式，還有 sprintf 做格式化的參考資料就放在這邊給各位使用<br>

* [How to work with complex numbers in C?](https://stackoverflow.com/a/9860772/7839373)
* [POPEN(3) Linux Programmer's Manual](http://man7.org/linux/man-pages/man3/popen.3.html)
* [C 語言中的 sprintf() 函數](http://ccckmit.wikidot.com/cp:sprintf)

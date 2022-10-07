+++
title = "Golang String Algorithm"
date = 2018-11-30T11:50:23+08:00
author = "Silen Mark"
cover = ""
tags = ["golang","alg"]
keywords = ["", ""]
description = ""
showFullContent = false
+++

### 一些关于字符串查找的算法
一些约定：

以下用 ``str`` 代表主串（也就是目标串，被检索的文本), ``pat`` 代表子串（也就时检索用的关键字 pattern )

#### 朴素算法
>朴素算法用白话讲就是：以主串每个字符开头，与子串进行匹配，最外层遍历主串，内层遍历子串,内层有不匹配时，外层从下一个字符开始，重新匹配子串。

#### KMP算法
>KMP算法，主串索引不回溯，子串根据第一次不匹配的字串索引查出对应`next`数组中的值，继续和主串接下来的字符比较。
>KMP 中`next`数组作用是：如果`pat`中第`j`个位置不匹配，则下次从`pat`的`next[j]`处开始比较。

<!--`next`数组构造-->



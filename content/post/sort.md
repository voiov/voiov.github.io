+++
title = "Sort"
date = 2018-12-02T10:20:31+08:00
author = "Silen Mark"
tags = ["sort","alg"]
keywords = ["", ""]
description = ""
showFullContent = false
+++
### 初级排序

#### 选择排序：
>最简单的排序算法：假设数组长度为`n`，从`i=0`( `i`是数组索引) 开始遍历数组，找到最小值，与第i个元素交换，如此往复，知道将整个数组排序。

#### 插入排序:
>选择排序：当前索引之前的所有元素都是有序的，但是他们最终位置还不确定，当索引到达数组的末尾时，数组排序就完成了。

#### 希尔排序：
>使数组中任意间隔为h的元素都是有序的，逐渐减小h到1即可完成排序。

```go
func ShellSort(a []int) {
    n := len(a)
    h := 1
    for h < n/3 { //寻找合适的间隔h
        h = 3*h + 1
    }
    for h >= 1 {
        //将数组变为间隔h个元素有序
        for i := h; i < n; i++ {
            //间隔h插入排序(将a[i]插入到a[i-h],a[i-2*h],a[i-3*h]...中)
            for j := i; j >= h && a[j] < a[j-h]; j -= h {
                swap(a, j, j-h)
            }
        }
        h /= 3
    }
}
func swap(slice []int, i int, j int) {
    slice[i], slice[j] = slice[j], slice[i]
}
```

#### 归并排序：


---
title: 基础算法
date: 2024-11-07 20:23:02
tags:
- 算法
---

## 排序

### 快排

``` python
def qsort(arr, l, r):
    if l > r:
        return
    x = q[l]
    i = l - 1
    j = r + 1
    while i < j:
        i += 1
        while not q[i] >= x:
            i += 1
        j -= 1
        while not q[j] <= x:
            j -= 1
        if i < j:
            temp = q[i]
            q[i] = q[j]
            q[j] = temp
    qsort(arr, l,j)
    qsort(arr, j+1,r)

```
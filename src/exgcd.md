# 扩展欧几里得算法

## 辗转相除法

引理: 如果有 a=bq+c , 则 (a,b) = (b,c).

显然, (a,b) = (b, a\%b) = \cdots = (r,0) = r. 这个序列是下降的, 因此必然是有限的.

## 扩展欧几里得

我们把带余除法的过程展开可以发现

```text
a可以写成b,c的线性组合
a ==> b, c
b ==> c, r_1
c ==> r_1, r_2
...
r_n-1 ==> r_n, r
r_n ==> r, 0
```

反过来, r可以写成r_n-1, r_n的线性组合... 最终可以得到 r可以写成a,b的线性组合, 组合的系数是ax+by=(a,b)的一组解.

如何用算法求出这组解呢?

我们把任务分解为两个部分

- 求出当b=0时, ax + by=(a,b)的解
- 用bx + (a%b)y = (b, a%b)的解, 表示ax+by=(a,b)的解

我们知道(a,b) = (b,a%b), a%b = a - floor(a/b) \* b;

如果x',y'是bx + (a%b)y = (b, a%b)的解, 代入并变形整理得到$a *y'+ b(x'-(a/b)y') = (a,b)$

因此我们知道了 (x',y') ==> (y', x'-(a/b)y')

以下是递归代码

```cpp
int exgcd(int a, int b, int &x, int &y) {
  if (b == 0) {
    x = 1;
    y = 0;
    return a;
  } else {
    int x1, y1;
    int gcd = exgcd(b, a % b, x1, y1);
    x = y1;
    y = x1 - (a / b) * y1;
    return gcd;
  }
}
```

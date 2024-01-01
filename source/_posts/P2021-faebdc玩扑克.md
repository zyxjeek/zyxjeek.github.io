title: P2021 faebdc玩扑克
date: '2024-01-01 12:28:16'
tags: OI
mathjax: true

---
## 1. 题目描述

> zky 有 $n$ 个扑克牌，编号从 $1$ 到 $n$，zky 把它排成一个序列，每次把最上方的扑克牌放在牌堆底，然后把下一张扑克牌拿出来输出，最终输出的序列恰好是从 $1$ 到 $n$，faebdc 问你原序列是什么，因为 faebdc 神犇早已在 $\mathcal O (1)$ 的时间得出结果，如果你在 1 s 内答不出来，faebdc 会吃了你。
> 对于 $100\%$ 的数据，$1 \le n \le {10}^6$。
>
> 原题链接：https://www.luogu.com.cn/problem/P2021

## 2. 思路

此题的数据范围为$10^6$，所以应该用$O(n)$级别的算法来解决。一开始比较容易想到的是使用数学方法进行推导，但是似乎有点复杂。考虑使用队列进行模拟，队列中储存的是答案在数组中的**下标**，每次输出就将数组中对应下标的答案设为当前应输出的数字（1~n）。这样即可解决问题。

建立一个数组$C$，表示整个扑克牌序列，一个队列$Q$，用于模拟整个过程，其中每个成员$i$表示第$i$张扑克牌。将$cnt$初始赋值为1。循环直到队列为空，每一次都将队首置于队尾，并取出第二个队首$k$，将$C_k$设为$cnt$，且递增$cnt$。循环结束后顺次输出数组$C$即可。

## 3. 代码

```C++
#include <bits/stdc++.h>
using namespace std;

int n;
int c[1000005];
queue<int> q;

int main() {
    cin >> n;
    for (int i = 1; i <= n; i++)
        q.push(i);
    int cnt = 1;
    while (!q.empty()) {
        q.push(q.front());
        q.pop();
        c[q.front()] = cnt++;
        q.pop();
    }
    for (int i = 1; i <= n; i++)
        cout << c[i] << ' ';
    return 0;
}

```

## 4. 复杂度分析

时间复杂度：$O(n)$

空间复杂度：$O(n)$



---

The END
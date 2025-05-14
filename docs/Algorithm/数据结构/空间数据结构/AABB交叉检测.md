---
categories: 
subtitle: 
draft: false
pin: false
title: AABB交叉检测
date : 2025-05-08
---
定义需要检测的矩阵 $A$ 和 $B$。

每个矩阵分别用左上角坐标和右下角坐标进行描述，这样，两个矩阵分别可以表示为 $(ax_{1},ay_{1}),(ax_{2},ay_{2})$ 和 $(bx_{1},by_{1}),(bx_{2},by_{2})$。

检测是否有重叠的代码如下
```cpp
bool isOverlap = ax1 <= bx2 && ax2 >= bx1 && ay1 <= by2 && ay2 >= by1;
```

这行代码有四个条件：
:material-numeric-1: $A$ 的上边界在 $B$ 的下边界上面。

:material-numeric-2: $A$ 的下边界在 $B$ 的上边界下面。

:material-numeric-3: $A$ 的左边界在 $B$ 的右边界左边。

:material-numeric-4: $A$ 的右边界在 $B$ 的左边界右边。


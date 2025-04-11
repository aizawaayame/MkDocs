---
date : 2025-04-10
title: sizeof
subtitle: 
draft: false
pin: false
categories: 
---
**指针**:  
	:material-numeric-1:指针大小永远固定。取决于 **编译的目标平台的位数** 。32 位就是 4 字节，64 位就是 8 字节。

**数组**：  
	:material-numeric-1:数组 **作为函数参数时会退化为指针** ，大小按指针计算。

**类**  
	:material-numeric-1:struct 结构体要考虑 **字节对齐** 。  
	:material-numeric-2:如果 class 配置了虚函数，则会在 **头部添加虚函数表** 。  
	:material-numeric-3:空类会用 1 个字节进行 **占位** 。

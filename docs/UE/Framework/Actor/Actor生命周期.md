---
categories: []
subtitle: 
draft: false
pin: false
title: Actor生命周期
date : 2025-05-07
---

![](https://d1iv7db44yhgxn.cloudfront.net/documentation/images/ad3b6cf4-7965-4a29-a44c-43183cf16fab/actorlifecycle1.png)  
/// Caption  
**Actor生命周期**  
///

## Create

创建Actor方式有以下几种：

:material-numeric-1: [[#Load From Disc|从磁盘加载]]

:material-numeric-2: [[#Play In Editor |Play In Editor]]

:material-numeric-3: [[#SpawnActor |SpawnActor]]

### Load From Disc

**从磁盘加载** 适用于关卡中已存在的 Actor：

:material-numeric-1: 调用 `UEngine::LoadMap` 时。

:material-numeric-2: 关卡流式传输调用 `UWorld::AddToWorld` 时。

### Play In Editor

**Play in Editor** 的Actor由编辑器中复制而来。

### SpawnActor

## BeginPlay

关卡开始后被调用。

## EndPlay

## GC

## :link: Reference

[Unreal Engine Actor Lifecycle | Unreal Engine 5.5 Documentation](https://dev.epicgames.com/documentation/en-us/unreal-engine/unreal-engine-actor-lifecycle)

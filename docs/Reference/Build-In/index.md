---
---

# 页面设置

[Reference - Material for MkDocs](https://squidfunk.github.io/mkdocs-material/reference/)

## 1. 设置Title

```
---
title: Lorem ipsum dolor sit amet 
---

# Page title
...
```

## 2. 设置描述

```
---
description: Nullam urna elit, malesuada eget finibus ut, ac tortor. 
---

# Page title
...
```

## 3. 设置Icon

```
---
icon: material/emoticon-happy 
---

# Page title
...
```

## 4. 设置状态

可以为每个页面分配一个状态，该状态将显示在导航侧边栏中。首先，通过将以下内容添加到 `mkdocs.yml` ，将状态标识符与描述关联起来：
```
extra:
  status:
    <identifier>: <description>
```

现在可以使用 frontmatter `status` 属性设置页面状态。例如，可以使用 Markdown 文件顶部的以下行将页面标记为 `new` ：
```
---
status: new
---

# Page title
...
```

以下的标识符已经预定义：

- :material-alert-decagram: – `new`
- :material-trash-can: – `deprecated`

参考[example for a custom page status](https://mkdocs-material.github.io/examples/page-status/)设置更多的状态。

## 5. 设置副标题

每个页面都可以定义一个副标题，使用 front matter `subtitle` 属性在导航侧边栏的标题下方呈现，并添加以下行：

```
---
subtitle: Nullam urna elit, malesuada eget finibus ut, ac tortor
---

# Page title
...
```

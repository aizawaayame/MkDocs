# 页面设置

## 设置Title

```
---
title: Lorem ipsum dolor sit amet 
---

# Page title
...
```

## 设置描述
```
---
description: Nullam urna elit, malesuada eget finibus ut, ac tortor. 
---

# Page title
...
```

## 设置Icon
```
---
icon: material/emoticon-happy 
---

# Page title
...
```

## 设置状态
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
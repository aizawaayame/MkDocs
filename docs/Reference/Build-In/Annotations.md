---
date created: 2025-04-02
date modified: 2025-04-03
---
[Annotations - Material for MkDocs](https://squidfunk.github.io/mkdocs-material/reference/annotations/#__codelineno-0-4)

## 1. Configuration

此配置允许将注释添加到所有内联和块级元素，以及代码块，并将注释相互嵌套。将以下行添加到 `mkdocs.yml` ：
```yaml
markdown_extensions:
  - attr_list
  - md_in_html
  - pymdownx.superfences
```
查看其他配置选项：
- [Attribute Lists  属性列表](https://squidfunk.github.io/mkdocs-material/setup/extensions/python-markdown/#attribute-lists)
- [Markdown in HTML  HTML 中的 Markdown](https://squidfunk.github.io/mkdocs-material/setup/extensions/python-markdown/#markdown-in-html)
- [SuperFences](https://squidfunk.github.io/mkdocs-material/setup/extensions/python-markdown-extensions/#superfences)


## 2. Usage

这是一段注释(1)。  
{.annotate}

1. :man_raising_hand: I'm an annotation! I can contain `code`, __formatted  
    text__, images, … basically anything that can be written in Markdown.

!!! note 注意事项  
	- `{.annotate}` 必须换行书写。  
	- 注释内容必须空一行。

### 2.1. 嵌套注释

这是外部注释(1)。  
{.annotate}

1.  :man_raising_hand: 这是内部注释(1)  
   {.annotate}
   
	1.  :woman_raising_hand: I'm an annotation as well!

### 2.2. Admonition中的注释

!!! note annotate " Admonition中的注释(1)"  
    - 不需要 `{.annotate}` 标记(2) 。  
	- 注释需要空一行。

1.  :man_raising_hand: I'm an annotation!
2.  :woman_raising_hand: I'm an annotation as well!

### 2.3. Content Tab中的注释

=== "Tab1"  
	注释1(1)  
	{.annotate}

	1. :man_raising_hand: I'm an annotation!
=== "Tab2"  
	注释2(1)  
	{.annotate}

	2. :woman_raising_hand: I'm an annotation as well!

### 2.4. HTML标签实现注释

<div class="annotate" markdown>

> Lorem ipsum dolor sit amet, (1) consectetur adipiscing elit.

</div>

1.  :man_raising_hand: I'm an annotation!

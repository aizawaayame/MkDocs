---
date created: 2025-04-03
date modified: 2025-04-03
tags: [adding-line-numbers]
---
[Code blocks - Material for MkDocs](https://squidfunk.github.io/mkdocs-material/reference/code-blocks/)
## Configuration

将以下行添加到 `mkdocs.yml` 中：
```yaml
markdown_extensions:
  - pymdownx.highlight:
      anchor_linenums: true
      line_spans: __span
      pygments_lang_class: true
  - pymdownx.inlinehilite
  - pymdownx.snippets
  - pymdownx.superfences
```

查看其他配置选项：

- [Highlight  突出显示](https://squidfunk.github.io/mkdocs-material/setup/extensions/python-markdown-extensions/#highlight)
- [InlineHilite](https://squidfunk.github.io/mkdocs-material/setup/extensions/python-markdown-extensions/#inlinehilite)
- [SuperFences](https://squidfunk.github.io/mkdocs-material/setup/extensions/python-markdown-extensions/#superfences)
- [Snippets  代码片段](https://squidfunk.github.io/mkdocs-material/setup/extensions/python-markdown-extensions/#snippets)

### 代码复制按钮

代码块可以自动在右侧渲染一个按钮，允许用户将代码块的内容复制到剪贴板。将以下内容添加到 `mkdocs.yml` 以全局启用它们：
```yaml
theme:
  features:
    - content.code.copy
```

### 代码选择按钮

代码块可以包含一个按钮，允许用户选择行范围，这非常适合链接到代码块的特定子部分。这允许用户动态应用行突出显示。将以下内容添加到 `mkdocs.yml` 以全局启用它：
```yaml
theme:
  features:
    - content.code.select
```

## Usage

### 添加标题

``` py title="bubble_sort.py"
def bubble_sort(items):
    for i in range(len(items)):
        for j in range(len(items) - 1 - i):
            if items[j] > items[j + 1]:
                items[j], items[j + 1] = items[j + 1], items[j]
```

### 添加注释

代码注释可以放置在代码块中的任何位置，只要该位置允许使用该代码块语言的注释即可。

```cpp
void main()
{
	func() // (1)
}
```

1.  :man_raising_hand: 这是一个func函数

如希望去除代码注释周围的注释字符，只需在代码注释的右括号后添加一个 `!` ：
```cpp
void main()
{
	func() // (1)!
}
```

1.  :man_raising_hand: 这是一个func函数

### 添加行号

通过在短代码后直接使用 `linenums="<start>"` 选项为代码块添加行号，其中 `<start>` 表示起始行号。代码块可以从 `1` 以外的行号开始，这样可以分割大型代码块以提高可读性：

``` py linenums="1"
def bubble_sort(items):
    for i in range(len(items)):
        for j in range(len(items) - 1 - i):
            if items[j] > items[j + 1]:
                items[j], items[j + 1] = items[j + 1], items[j]
```

### 高亮特定行

通过将行号传递给位于语言简码之后的 `hl_lines` 参数，可以突出显示特定的行。行数从 `1` 开始计数，无论指定为 `linenums`的起始行号是多少：

=== "Lines"

    ```` markdown title="Code block with highlighted lines"
    ``` py hl_lines="2 3"
    def bubble_sort(items):
        for i in range(len(items)):
            for j in range(len(items) - 1 - i):
                if items[j] > items[j + 1]:
                    items[j], items[j + 1] = items[j + 1], items[j]
    ```
    ````

    <div class="result" markdown>

    ``` py linenums="1" hl_lines="2 3"
    def bubble_sort(items):
        for i in range(len(items)):
            for j in range(len(items) - 1 - i):
                if items[j] > items[j + 1]:
                    items[j], items[j + 1] = items[j + 1], items[j]
    ```

    </div>

=== "Line ranges"

    ```` markdown title="Code block with highlighted line range"
    ``` py hl_lines="3-5"
    def bubble_sort(items):
        for i in range(len(items)):
            for j in range(len(items) - 1 - i):
                if items[j] > items[j + 1]:
                    items[j], items[j + 1] = items[j + 1], items[j]
    ```
    ````

    <div class="result" markdown>

    ``` py linenums="1" hl_lines="3-5"
    def bubble_sort(items):
        for i in range(len(items)):
            for j in range(len(items) - 1 - i):
                if items[j] > items[j + 1]:
                    items[j], items[j + 1] = items[j + 1], items[j]
    ```

    </div>

  [Adding line numbers]: #adding-line-numbers

### 高亮内联代码块

  当启用 InlineHilite 时，可以通过在内联代码块前加上一个 #! ，然后紧跟相应的语言简码，来将语法高亮应用于内联代码块。

  ``` markdown title="Inline code block"
The `#!python range()` function is used to generate a sequence of numbers.
```

<div class="result" markdown>

The `#!python range()` function is used to generate a sequence of numbers.

</div>

### 嵌入外部文件

启用代码片段后，可以通过直接在代码块中使用 --8<-- 符号来嵌入来自其他文件（包括源文件）的内容：

```` markdown title="Code block with external content"
``` title=".browserslistrc"
;--8<-- ".browserslistrc"
```
````

<div class="result" markdown>

``` title=".browserslistrc"
last 4 years
```

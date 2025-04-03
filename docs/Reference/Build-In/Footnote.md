---
date created: 2025-04-03
date modified: 2025-04-03
---
[Footnotes - Material for MkDocs](https://squidfunk.github.io/mkdocs-material/reference/footnotes/)

## Configuration

将以下行添加到 `mkdocs.yml` ：

```yaml
markdown_extensions:
  - footnotes
```

查看其他配置选项：

- [Footnotes  脚注](https://squidfunk.github.io/mkdocs-material/setup/extensions/python-markdown/#footnotes)

## Usage

### 添加脚注引用

脚注参考必须用方括号括起来，并且必须以插入符号 ^ 开头，紧接着是任意标识符，这类似于标准 Markdown 链接语法。

``` title="Text with footnote references"
Lorem ipsum[^1] dolor sit amet, consectetur adipiscing elit.[^2]
```

<div class="result" markdown>

Lorem ipsum[^1] dolor sit amet, consectetur adipiscing elit.[^2]

</div>

### 添加单行脚注

``` title="Footnote"
[^1]: Lorem ipsum dolor sit amet, consectetur adipiscing elit.
```

<div class="result" markdown>

[:octicons-arrow-down-24: Jump to footnote](#fn:1)

</div>

  [^1]: Lorem ipsum dolor sit amet, consectetur adipiscing elit.

### 添加多行脚注

段落可以写在下一行，并且必须缩进四个空格：

``` title="Footnote"
[^2]:
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod
    nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor
    massa, nec semper lorem quam in massa.
```

<div class="result" markdown>

[:octicons-arrow-down-24: Jump to footnote](#fn:2)

</div>

[^2]:
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod
    nulla. Curabitur feugiat, tortor non consequat finibus, justo purus
    auctor massa, nec semper lorem quam in massa.
---
date created: 2025-04-03
date modified: 2025-04-03
---
[Formatting - Material for MkDocs](https://squidfunk.github.io/mkdocs-material/reference/formatting/)

## Configuration

将以下行添加到 `mkdocs.yml` :

```yaml
markdown_extensions:
  - pymdownx.critic
  - pymdownx.caret
  - pymdownx.keys
  - pymdownx.mark
  - pymdownx.tilde
```

查看其他配置选项：

- [Critic](https://squidfunk.github.io/mkdocs-material/setup/extensions/python-markdown-extensions/#critic)
- [Caret, Mark & Tilde  
    插入符号、标记和波浪号](https://squidfunk.github.io/mkdocs-material/setup/extensions/python-markdown-extensions/#caret-mark-tilde)
- [Keys  按键](https://squidfunk.github.io/mkdocs-material/setup/extensions/python-markdown-extensions/#keys)

## Usage

### 高亮

#### Html语法

``` title="Text with html"

<div class="result" markdown>

<del class="critic">删除</del>

<ins class="critic">添加</ins>

<del class="critic">删除</del><ins class="critic">替换</ins>

<mark class="critic">高亮</mark>

<span class="critic comment">注释</span>.

<div>
  <mark class="critic block">
    <p>
      格式化也可以应用于块，通过将打开和关闭标签放在单独的行上，并在标签和内容之间添加新行。
    </p>
  </mark>
</div>

</div>

```

<div class="result" markdown>

<del class="critic">删除</del>

<ins class="critic">添加</ins>

<del class="critic">删除</del><ins class="critic">替换</ins>

<mark class="critic">高亮</mark>

<span class="critic comment">注释</span>.

<div>
  <mark class="critic block">
    <p>
      格式化也可以应用于块，通过将打开和关闭标签放在单独的行上，并在标签和内容之间添加新行。
    </p>
  </mark>
</div>

</div>

#### Markdown语法

``` title="Text with highlighting"

- ==This was marked (highlight)==

- ^^This was inserted (underline)^^

- ~~This was deleted (strikethrough)~~

```

<div class="result" markdown>

- ==This was marked (highlight)==
- ^^This was inserted (underline)^^
- ~~This was deleted (strikethrough)~~

</div>

### 上标和下标

``` title="带有下标和上标的文本"

H~2~O

X^2^

```

<div class="result" markdown  >

H~2~O

X^2^

</div>

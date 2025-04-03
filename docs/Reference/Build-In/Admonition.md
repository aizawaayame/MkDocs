---
date created: 2025-04-02
date modified: 2025-04-02
---
[Admonitions - Material for MkDocs](https://squidfunk.github.io/mkdocs-material/reference/admonitions/#inline-blocks-inline-end)

## Configuration

将以下行添加到 `mkdocs.yml` :
```yaml
markdown_extensions:
  - admonition
  - pymdownx.details
  - pymdownx.superfences
```

其他配置选项：
- [Admonition  提示](https://squidfunk.github.io/mkdocs-material/setup/extensions/python-markdown/#admonition)
- [Details  详情](https://squidfunk.github.io/mkdocs-material/setup/extensions/python-markdown-extensions/#details)
- [SuperFences](https://squidfunk.github.io/mkdocs-material/setup/extensions/python-markdown-extensions/#superfences)

每个支持的 Admonition 类型都有一个独特的图标，支持更改为主题自带的任何图标，支持自定义图标。将以下行添加到 `mkdocs.yml` 中：
```yaml
theme:
  icon:
    admonition:
      <type>: <icon>
```

## Usage

### 类型

!!! note "note"  
    note  
!!! abstract "abstract"  
	abstract  
!!! info "info"  
	info  
!!! tip  
	tip  
!!! success  
	success  
!!! question  
	question  
!!! warning  
	warning  
!!! failure  
	failure  
!!! danger  
	danger  
!!! bug  
	bug  
!!! example  
	example  
!!! quote  
	quote

### 嵌套

!!! note "Outer"  
	outer  
	!!! note "Inner"  
		inner

### 可折叠的块

??? note  
	可折叠  
???+ note  
	可折叠且默认展开

### 内联块

提示框也可以呈现为内联块（例如，用于侧边栏），使用 `inline` + `end` 修饰符将其放置在右侧，或者仅使用 `inline` 修饰符将其放置在左侧：

=== ":octicons-arrow-right-16: inline end"  
    !!! info inline end "Lorem ipsum"  
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et  
        euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo  
        purus auctor massa, nec semper lorem quam in massa.  
    ```  
    !!! info inline end "Lorem ipsum"  
        Lorem ipsum dolor sit amet, consectetur  
        adipiscing elit. Nulla et euismod nulla.  
        Curabitur feugiat, tortor non consequat  
        finibus, justo purus auctor massa, nec  
        semper lorem quam in massa.  
    ```  
    Use `inline end` to align to the right (left for rtl languages).  
=== ":octicons-arrow-left-16: inline"  
    !!! info inline "Lorem ipsum"  
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et  
        euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo  
        purus auctor massa, nec semper lorem quam in massa.  
    ``` markdown  
    !!! info inline "Lorem ipsum"  
        Lorem ipsum dolor sit amet, consectetur  
        adipiscing elit. Nulla et euismod nulla.  
        Curabitur feugiat, tortor non consequat  
        finibus, justo purus auctor massa, nec  
        semper lorem quam in massa.  
    ```  
    Use `inline` to align to the left (right for rtl languages).

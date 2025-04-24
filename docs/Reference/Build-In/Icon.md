---
date : 2025-04-03
title: Icon
subtitle: 
draft: false
pin: false
categories: 
date created: 2025-04-03
date modified: 2025-04-03
---

## Search

[Icons, Emojis - Material for MkDocs](https://squidfunk.github.io/mkdocs-material/reference/icons-emojis/)

<div class="mdx-iconsearch" data-mdx-component="iconsearch">
  <input
    class="md-input md-input--stretch mdx-iconsearch__input"
    placeholder="Search the icon and emoji database"
    data-mdx-component="iconsearch-query"
  />
  <div class="mdx-iconsearch-result" data-mdx-component="iconsearch-result">
    <select
      class="mdx-iconsearch-result__select"
      data-mdx-component="iconsearch-select"
    >
      <option value="all" selected>All</option>
      <option value="icons">Icons</option>
      <option value="emojis">Emojis</option>
    </select>
    <div class="mdx-iconsearch-result__meta"></div>
    <ol class="mdx-iconsearch-result__list"></ol>
  </div>
</div>
<small>
  :octicons-light-bulb-16:
  **Tip:** Enter some keywords to find icons and emojis and click on the
  shortcode to copy it to your clipboard.
</small>

## Configuration

将以下行添加到 `mkdocs.yml` ：

```yaml
markdown_extensions:
  - attr_list
  - pymdownx.emoji:
      emoji_index: !!python/name:material.extensions.emoji.twemoji
      emoji_generator: !!python/name:material.extensions.emoji.to_svg
```

Material for MkDocs 捆绑了以下图标集：

- :material-material-design: – [Material Design]
- :fontawesome-brands-font-awesome: – [FontAwesome]
- :octicons-mark-github-16: – [Octicons]
- :simple-simpleicons: – [Simple Icons]

## Usage

### Emoji

``` title="Emoji"
:smile:
```
可以在 Markdown 中集成表情符号，方法是将表情符号的短代码放在两个冒号之间。如果您使用的是 [Twemoji] (recommended)，可以在 [Emojipedia] 上查找短代码：
<div class="result" markdown>

:smile:

</div>
  [Twemoji]: https://github.com/jdecked/twemoji
  [Emojipedia]: https://emojipedia.org/twitter/

### Icon

启用 Emoji 后，可以通过引用主题捆绑的任何图标的有效路径来使用图标，类似于表情符号，这些图标位于 .icons 目录中，并将 / 替换为 - ：

``` title="Icon"
:fontawesome-regular-face-laugh-wink:
```

<div class="result" markdown>

:fontawesome-regular-face-laugh-wink:

</div>

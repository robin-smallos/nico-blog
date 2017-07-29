# 强调

Markdown 使用 `*` （星号）和 `_` （下划线）作为强调的标记，被单个 `*` （星号）或 `_` （下划线）包含的文字会被转换成 HTML 的 `<em>` 标签；两个 `*` （星号）或 `_` （下划线）将会被转换成 HTML 的 `<strong>` 标签。

**例如**：

    *single asterisks*

    _single underscores_

    **double asterisks**

    __double underscores__

**将会转换为**：

    <em>single asterisks</em>

    <em>single underscores</em>

    <strong>double asterisks</strong>

    <strong>double underscores</strong>

你可以根据喜好选择使用哪种方式；唯一的限制就是用于强调的开头和结尾的字符要保持一致。

强调也可以直接插入在字符中间：

    un*frigging*believable

如果你的 `*` （星号）或 `_` （下划线）两边有空白，那么它将直接被作为星号或下划线显示。

要在某个位置插入 `*` （星号）或 `_` （下划线），你可以使用反斜线对齐进行转义：

    \*this text is surrounded by literal asterisks\*

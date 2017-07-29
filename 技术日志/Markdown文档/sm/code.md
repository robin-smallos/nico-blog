# 程序代码

要标识出一小段程序代码，你可以使用 `` ` `` （反引号）将其包住。不像格式化的区块代码那样，一小段程序代码的范围可以存在于正常的段落之中。

**例如**：

    Use the `printf()` function.

**将会生成**：

    <p>Use the <code>printf()</code> function.</p>

如果想要在一小段程序代码中插入 `` ` `` （反引号），你可以再外多个反引号将其包住即可。

强调也可以直接插入在字符中间：

    ``There is a literal backtick (`) here.``

**将会生成**：

    <p><code>There is a literal backtick (`) here.</code></p>

程序代码的开头和末尾可以各加入空格，即在在开头后面和末尾的前面。这样你就可以在程序代码的开头和末尾插入反引号了：

    A single backtick in a code span: `` ` ``

    A backtick-delimited string in a code span: `` `foo` ``

**将会生成**：

    <p>A single backtick in a code span: <code>`</code></p>

    <p>A backtick-delimited string in a code span: <code>`foo`</code></p>

在程序代码内，`&` （and 符号）和尖括号都将会被转换成 HTML 实体字符，这样就比较容易在 Markdown 中插入 HTML 源码。Markdown 会把下面这段：

    Please don't use any `<blink>` tags.

**转换成**：

    <p>Please don't use any <code>&lt;blink&gt;</code> tags.</p>

你可以这么写：

    `&#8212;` is the decimal-encoded equivalent of `&mdash;`.

**将会生成**：

    <p><code>&amp;#8212;</code> is the decimal-encoded equivalent of <code>&amp;mdash;</code>.</p>

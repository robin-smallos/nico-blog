# 链接

Markdown 支持 **行内链接** 和 **参考链接** 两种类型的链接。

不管是以上哪种类型的链接，其文本都是使用[方括号]来标记。

要创建一个行内链接，只需在方括号后面紧接着小括号，将网址链接插入其中即可。如果你还想给链接加上可选的标题（title），只要用 `"` （双引号）把标题文本包住即可。

**例如**：

    This is [an example](http://example.com/ "Title") inline link.

    [This link](http://example.net/) has no title attribute.

**显示为**：

This is [an example](http://example.com/ "Title") inline link.

[This link](http://example.net/) has no title attribute.

如果你想将链接关联到同一个服务器下的本地资源，你也可以使用相对路径。

**例如**：

    See my [About](/about/) page for details.

参考类型的链接跟在第一组方括号后面的方括号内，只要往里面加入可以识别链接的标签即可。

**例如**：

    This is [an example][id] reference-style link.

你也可以选择性的在两个方括号间加入 ` `（空格）以示区分。

**例如**：

    This is [an example] [id] reference-style link.

接下来，你可以在文档的任何地方，标识出这个标签的链接地址，让其独占一行。

**例如**：

    [id]: http://example.com/  "Optional Title Here"

其形式是

  - 方括号包含着链接的识别符（可以选择性的使用三个空格与左边距缩进以示区分）
  - 接着一个 `:` 冒号
  - 接着一个或以上的 ` ` （空格）或者 `Tab`
  - 接着链接的地址
  - 选择性的接着链接的标题（title）属性，可以使用 `'` （单引号）、`"` （双引号）或者 `()` （小括号）将其闭合。

以下这三种链接的定义都是相同的：

**例如**：

    [foo]: http://example.com/  "Optional Title Here"
    [foo]: http://example.com/  'Optional Title Here'
    [foo]: http://example.com/  (Optional Title Here)

**请注意**：在 Markdown.pl 1.0.1 中有个已知的问题，它会防止单引号用来区分链接的标题（title）属性（换言之就是忽略单引号）。

链接地址也可以选择性地使用尖括号闭合。

**例如**：

    [id]: <http://example.com/>  "Optional Title Here"

你也可以把标题（title）属性放在下一行，用额外的 ` ` （空格）或者 `Tab` 增加边距，这样能让较长的链接地址看起来更加美观。

**例如**：

    [id]: http://example.com/longish/path/to/resource/here
        "Optional Title Here"

链接定义只用于在 Markdown 处理的过程中生成链接，当你从 HTML 文档输出的时候，链接定义是会被移除的。

链接标识符通常由字母，数字，空格和标点符号组成，但它们是不区分大小写的。

**例如**：

    [link text][a]
    [link text][A]

以上两个链接是一样的。

*隐式链接* 允许你忽略掉链接的名称，链接地址和链接文本相同。只要使用空的方括号即可。例如 “Google” 链接到 google.com 这个地址，你可以简写成：

    [Google][]

接着定义链接内容：

    [Google]: http://google.com/

由于链接内容可能包含空格，这种简写方式对于多个文字的链接文本也是有效的：

    Visit [Daring Fireball][] for more information.

然后接着定义链接：

    [Google]: http://google.com/

链接定义可以放在 Markdown 文档的任何地方。我比较倾向于放在紧跟着的每个段落的后面，如果你愿意，也可以把它们都放在文档的末尾，就想文章的注解一样。

以下是一个链接定义的范例：

    I get 10 times more traffic from [Google] [1] than from [Yahoo] [2] or [MSN] [3].

      [1]: http://google.com/        "Google"
      [2]: http://search.yahoo.com/  "Yahoo Search"
      [3]: http://search.msn.com/    "MSN Search"

如果写成 *隐式链接*，可以这么来：

    I get 10 times more traffic from [Google][] than from [Yahoo][] or [MSN][].

      [google]: http://google.com/        "Google"
      [yahoo]:  http://search.yahoo.com/  "Yahoo Search"
      [msn]:    http://search.msn.com/    "MSN Search"

以上两种写法都会生成下面的 HTML：

    <p>I get 10 times more traffic from <a href="http://google.com/" title="Google">Google</a> than from <a href="http://search.yahoo.com/" title="Yahoo Search">Yahoo</a> or <a href="http://search.msn.com/" title="MSN Search">MSN</a>.</p>

为了比较，以下是用 Markdown 行内链接写的相同段落：

    I get 10 times more traffic from [Google](http://google.com/ "Google") than from [Yahoo](http://search.yahoo.com/ "Yahoo Search") or [MSN](http://search.msn.com/ "MSN Search").

参考类型的链接重点在于书写起来麻烦，但是文档源码具有很好的可读性。通过以上例子的比较可以发现，使用参考类型的链接写法，段落本身只有 81 个字符，而行内链接则有 176 个字符，如果是纯 HTML 的话，有 234 个字符。在纯 HTML 当中，标签比文本还多。

使用 Markdown 的参考类型链接，源文档更接近于浏览器最终渲染的输出结果。通过把跟标签相关的元数据移到段落之外，你可以添加链接而不打断文章整体的连贯性。

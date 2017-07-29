# 代码区块

Markdown 使用 `<pre>` 和 `<code>` 标签把代码区块包裹起来。这样的代码会按照其原本的排版或者书写方式显示出来。想要在 Markdown 中创建一个代码区块很简单，只需要在内容的开头使用四个空格或者一个 tab 就可以。

**例如**：

    这是一个普通段落：
    
        这是一个代码区块。

**显示为**：

这是一个普通段落：

    这是一个代码区块。

同一级的缩进（四个空格或者一个 tab）将会从代码区块的每行移除。

**例如**：

    Here is an example of AppleScript:
    
        tell application "Foo"
            beep
        end tell

**显示为**：

Here is an example of AppleScript:

    tell application "Foo"
        beep
    end tell

代码区块的范围会一直延伸到没有缩进的那一行（或者延伸到文章的末尾）。

在代码区块中，`&` （And 符号）、`<` 和 `>` （尖括号）会自动转换为 HTML 实体字符。这样一来，在 Markdown 中插入 HTML 源代码就非常简单了。只需要复制和粘贴之，Markdown 就会帮你搞定这些编码的麻烦。

**例如**：

        <div class="footer">
                &copy; 2015 Foo Corporation
        </div>

**显示为**：

    <div class="footer">
            &copy; 2015 Foo Corporation
    </div>

在代码区块中，一般的 Markdown 语法不会被转换。例如：`*` （星号）还是原来的星号。这意味着你用 Markdown 书写 Markdown 语法相关的文档是很容易的。

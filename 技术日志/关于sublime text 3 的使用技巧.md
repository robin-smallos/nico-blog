## 关于sublime text 3 的使用技巧.md

- 完全卸载sublime text 3
    + 因为刚开始瞎折腾搞了很多插件，导致后来运行出现问题，老弹床窗，并且安装插件直接爆 无法连接，所以打算重装。
    + 重装顺序，sublime text->preferences->browse packages 打开这个目录！全删，然后再把sublime丢垃圾桶，进行重装搞定

- 插件推荐
    + MarkdownEditing
        * 简介：MarkdownEditing是Markdown写作者必备的插件，它可以不仅可以高亮显示Markdown语法还支持很多编程语言的语法高亮显示。
        * 常用快捷键：
            - command + option + k 插入链接
            - command + shift + k 插入图片
    + OmniMarkupPreviewer
        * 简介：OmniMarkupPreviewer用来预览markdown 编辑的效果，同样支持渲染代码高亮的样式。
        * 常用快捷键
            - Command +Option +O: 在浏览器中预览
            - Command+Option+X: 导出HTML
            - Ctrl+Alt+C: HTML标记拷贝至剪贴板

###操作技巧

-    1.Command+O可以实现头文件和源文件之间的快速切换
-    2.一片区域的所有行进行同时编辑，Command+Shift+L可以将当前选中区域打散，然后进行同时编辑
-    3.打散自然就有合并，Command＋J 可以把当前选中区域合并为一行
-    4.在Command+P匹配到文件后，我们可以进行后续输入以跳转到更精确的位置：
    +    @ 符号跳转：输入@symbol跳转到symbol符号所在的位置
    +    \# 关键字跳转：输入#keyword跳转到keyword所在的位置
    +    : 行号跳转：输入:12跳转到文件的第12行。
-    5. command + option + <数字> 进行分屏


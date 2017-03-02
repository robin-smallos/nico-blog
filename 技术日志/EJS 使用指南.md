##安装##
$ npm install ejs
##特性##
<% %> 用于控制流
<%= %> 用于转义的输出
<%- %> 用于非转义的输出
-%> 结束标签用于换行移除模式
带有<%_ _%>的控制流使用空白字符移除模式
自定义分隔符 (例如，使用 '<? ?>' 代替 '<% %>')
包含
客户端支持
中介JavaScript的静态缓存
模板的静态缓存
与 Express 视图系统兼容

##示例##
<% if (user) { %>
  <h2><%= user.name %></h2>
<% } %>

##用法##
var template = ejs.compile(str, options);
template(data);
// => 渲染 HTML 字符串

ejs.render(str, data, options);
// => 渲染 HTML 字符串
你也可以使用快捷方式 ejs.render(dataAndOptions); ，其中你可以通过一个对象来传递任何东西。在这种情况下，你需要以一个装有所有需要传递对象的本地变量结束。

##选项##
cache 编译过的函数会被缓存，需要filename
filename 被cache用做缓存的键，用于包含
context 函数执行的上下文
compileDebug 如果为false，不会编译调试用的工具
client 返回独立的编译后的函数
delimiter 开启或者闭合尖括号所用的字符
debug 输出生成的函数体
_with 是否使用 with() {} 结构。如果为 false 则局部数据会储存在 locals 对象中。
rmWhitespace 移除所有可以安全移除的空白字符，包含前导和尾后的空白字符。同时会为所有scriptlet标签开启-%>换行截断的更加安全的模式。（它不会在一行之中去除标签的换行）。

##标签##
<% 'Scriptlet' 标签, 用于控制流，没有输出
<%= 向模板输出值（带有转义）
<%- 向模板输出没有转义的值
<%# 注释标签，不执行，也没有输出
<%% 输出字面的 '<%'
%> 普通的结束标签
-%> Trim-mode ('newline slurp') 标签, 移除随后的换行符

##包含##
包含要么是绝对路径，或者如果不是的话，被视为相对于调用include的模板的路径（需要filename选项）。 例如，你在./views/users.ejs中包含./views/user/show.ejs，你应该使用<%- include('user/show') %>。

你可能会用到原始输出标签（<%-）避免二次转义HTML输出。

<ul>
  <% users.forEach(function(user){ %>
    <%- include('user/show', {user: user}) %>
  <% }); %>
</ul>
包含的内容在运行时插入， 所以你可以在include调用中使用变量作为路径（例如<%- include(somePath) %>）。在你顶级数据对象中的变量都可以用于所有的包含，而局部变量需要传递进来。

注意：仍然支持包含预处理指令（<% include user/show %>）。

##自定义分隔符##
自定义分隔符可以以模板为单位应用，或者全局：

var ejs = require('ejs'),
    users = ['geddy', 'neil', 'alex'];

// Just one template
ejs.render('<?= users.join(" | "); ?>', {users: users}, {delimiter: '?'});
// => 'geddy | neil | alex'

// Or globally
ejs.delimiter = '$';
ejs.render('<$= users.join(" | "); $>', {users: users});
// => 'geddy | neil | alex'
##缓存##
EJS 自带了一个基本的运行时缓存，用于缓存渲染模板的中介JavaScript函数。使用 Node 的 lru-cache 库来添加LRU缓存十分简单：

var ejs = require('ejs')
  , LRU = require('lru-cache');
ejs.cache = LRU(100); // LRU cache with 100-item limit
如果你想清除ejs的缓存，调用ejs.clearCache。如果你需要以一个不同的限额来使用LRU，只需要将ejs.cache重新设置为一个LRU的新实例。

##布局##
EJS 不会特别地支持区块，但是可以采用包含头部和尾部的方法来实现局部，像这样：

<%- include('header') -%>
<h1>
  Title
</h1>
<p>
  My page
</p>
<%- include('footer') -%>

##客户端支持##
访问最新发布，下载
./ejs.js 或者 ./ejs.min.js。

选择其一包含到你的页面中，并且使用 ejs.render(str)。
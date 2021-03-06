MongoDB基础知识.md

##  MongoDB的基本概念
    -   文档是MongoDB中数据的基本单元，非常类似于关系型数据库管理系统中的行，但更有表现力
    -   类似的，集合(collection) 可以看做是一个拥有动态模式(dynamic schema)的表。
    -   MongoDB 的一个实例可以拥有多个相互独立的数据库 (database)，每一个数据库都拥有自己的集合
    -   每一个文档都有一个特殊的健"_id"，这个键在文档所属的集合中是唯一的。
    -   MongoDB 自带一个简单但功能强大的JavaScript shell，可用于管理MongoDB的实例或数据操作

##  数据类型
    近似于json，但是又扩充了几大类
    -   null
        +   null用于表示空值或者不存在的字段：
            *   {"x": null}
    -   布尔型
        +   true & false
            *   {"x": true}
    -   数值
        +   shell默认使用64位浮点型数值。因此，一下数值在shell中是很正常的：
            *   {"x": 3,14}
            *   {"x": 3}
        +   对于整数值，可使用NumberInt类（表示4字节带符号整数)或NumberLong类（表示8字符带符号整数)
            *   {"x": NumerInt("3")}
            *   {"x": NumerLong("3")}
        +   字符串
            UTF-8字符串都可表示为字符串类型的数据：
            *   {"x": "footer"}
        +   日期
            日期被存储为自新纪元以来经过的毫秒数，不存储时区
            *   {"x": new Date()}
        +   正则表达式
            *   查询时，使用正则表达式作为限定条件，语法同js
            *   {"x": /foobar/i}
        +   数组
            *   数据列表或数据集可以表示为数组
            *   {"x": ["a", "b", "c"]}
        +   内嵌文档
            *   文档可嵌套其他文档，被嵌套的文档作为父文档的值
            *   {"x": ["foo": "bar"]}
        +   对象id
            *   对象id是一个12字节的id，是文档的唯一标识。
            *   {"x": ObjectId()}
        +   二进制数据
            *   二进制数据是一个任意字节的字符串。它不能直接在shell中使用。如果将非UTF-8字符保存到数据库中，二进制数据是唯一的方式
        +   代码
            *   查询和文档中可以包括任意JavaScript代码：
            *   {"x": function(){/* ... */}}
        +   其他待看







